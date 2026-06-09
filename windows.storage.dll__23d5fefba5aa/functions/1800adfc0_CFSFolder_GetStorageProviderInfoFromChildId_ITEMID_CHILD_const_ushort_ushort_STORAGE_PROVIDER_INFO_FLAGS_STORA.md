# CFSFolder::_GetStorageProviderInfoFromChildId(_ITEMID_CHILD const *,ushort * *,ushort * *,STORAGE_PROVIDER_INFO_FLAGS *,STORAGE_PROVIDER_PATH_COMPARE_FLAGS *,ushort * *,ushort * *,IStorageProviderHandlerPriv * *)

- ea: `0x1800adfc0`
- end: `0x1800ae63c`
- name: `?_GetStorageProviderInfoFromChildId@CFSFolder@@IEAAJPEFBU_ITEMID_CHILD@@PEAPEAG1PEAW4STORAGE_PROVIDER_INFO_FLAGS@@PEAW4STORAGE_PROVIDER_PATH_COMPARE_FLAGS@@11PEAPEAUIStorageProviderHandlerPriv@@@Z`
- size: `1660`
- prototype: `__int64 __fastcall(CFSFolder *__hidden this, const struct _ITEMID_CHILD *, unsigned __int16 **, unsigned __int16 **, enum STORAGE_PROVIDER_INFO_FLAGS *, enum STORAGE_PROVIDER_PATH_COMPARE_FLAGS *, unsigned __int16 **, unsigned __int16 **, struct IStorageProviderHandlerPriv **)`
- caller_count: `9`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800bd610`
- `0x1800e98d0`
- `0x180167710`
- `0x18025f9e0`
- `0x18029a67c`
- `0x1802a8710`
- `0x1805252ec`
- `0x18052c6a0`
- `0x18052cda0`

## callees

- `0x180009fc0`
- `0x180063050`
- `0x1800adfc0`
- `0x1800ae980`
- `0x1800aeb90`
- `0x1800fa660`
- `0x1803b1f60`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x1800ae498`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x1800ae498`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x1800ae0ea`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x1800ae0ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ae255`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ae255`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae182`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae1db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae2de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae39f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae529`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae55d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae577`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae182`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae1db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae2de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae39f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae529`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae55d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae577`

## string_xrefs

- `0x1800ae20b`: `computer`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CFSFolder::_GetStorageProviderInfoFromChildId(
        CFSFolder *this,
        const struct _ITEMID_CHILD *a2,
        unsigned __int16 **a3,
        LPVOID *a4,
        enum STORAGE_PROVIDER_INFO_FLAGS *a5,
        enum STORAGE_PROVIDER_PATH_COMPARE_FLAGS *a6,
        unsigned __int16 **a7,
        unsigned __int16 **a8,
        struct IStorageProviderHandlerPriv **a9)
{
  CFSFolder *v9; // rbx
  __int64 v10; // r13
  bool v11; // r13
  char *v12; // rdi
  __int64 (__fastcall *v13)(char *, void *, __int64, __int64); // rbx
  __int64 v14; // rax
  HRESULT v15; // edi
  void *v16; // rdi
  __int64 (__fastcall *v17)(void *, LPVOID, __int64 **, LPVOID *, int *); // rbx
  int v18; // eax
  __int64 *v19; // rcx
  void *v20; // rcx
  unsigned __int16 *v21; // r15
  unsigned __int64 v22; // r12
  const wchar_t *v23; // rdi
  unsigned __int64 v24; // rbx
  unsigned __int64 v25; // rsi
  wchar_t *v26; // rax
  wchar_t *v27; // rdx
  int v28; // r14d
  wchar_t v29; // ax
  wchar_t *v30; // rcx
  unsigned __int16 *v32; // rax
  void *v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  LPWSTR v36; // rbx
  LPWSTR v37; // rcx
  unsigned __int16 *v38; // rax
  unsigned __int16 *v39; // rax
  unsigned __int16 *v40; // rax
  __int64 v41; // rcx
  __int64 *v42; // rdi
  __int64 (__fastcall *v43)(__int64 *, GUID *, __int64 *); // rbx
  __int64 v44; // rax
  char v47; // [rsp+40h] [rbp-91h] BYREF
  LPWSTR pszPath; // [rsp+48h] [rbp-89h] BYREF
  __int64 *v49; // [rsp+50h] [rbp-81h] BYREF
  void *ppv; // [rsp+58h] [rbp-79h] BYREF
  __int64 v51; // [rsp+60h] [rbp-71h] BYREF
  int v52; // [rsp+68h] [rbp-69h] BYREF
  int v53; // [rsp+6Ch] [rbp-65h] BYREF
  LPVOID v54; // [rsp+70h] [rbp-61h] BYREF
  LPVOID v55; // [rsp+78h] [rbp-59h] BYREF
  __int64 v56; // [rsp+80h] [rbp-51h]
  __int64 v57; // [rsp+88h] [rbp-49h]
  LPVOID pv; // [rsp+90h] [rbp-41h] BYREF
  __int64 v59; // [rsp+98h] [rbp-39h]
  __int64 v60; // [rsp+A0h] [rbp-31h]
  LPVOID v61; // [rsp+A8h] [rbp-29h] BYREF
  __int64 v62; // [rsp+B0h] [rbp-21h]
  __int64 v63; // [rsp+B8h] [rbp-19h]
  CFSFolder *v64; // [rsp+C0h] [rbp-11h]

  ppv = a2;
  v9 = this;
  v64 = this;
  pszPath = (LPWSTR)a9;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *(_DWORD *)a5 = 0;
  if ( a6 )
    *(_DWORD *)a6 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a9 )
    *a9 = 0;
  v47 = 1;
  v54 = &v47;
  _lambda_ea9c6a719f4a9bb818bf1c421ccbcdfc_::operator()(&v54);
  v10 = -1;
  if ( !v47 )
    goto LABEL_30;
  v11 = 0;
  v54 = 0;
  v12 = (char *)v9 + 312;
  v13 = *(__int64 (__fastcall **)(char *, void *, __int64, __int64))(*((_QWORD *)v9 + 39) + 112LL);
  v14 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v54);
  v15 = v13(v12, ppv, 3, v14);
  if ( v15 >= 0 )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v15 = SHCoCreateInstance(0, &CLSID_SyncRootManager, 0, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &ppv);
    if ( v15 < 0 )
    {
LABEL_24:
      v20 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
      }
      goto LABEL_26;
    }
    v49 = 0;
    v53 = 0;
    pv = 0;
    v59 = 0;
    v60 = 0;
    v16 = ppv;
    v17 = *(__int64 (__fastcall **)(void *, LPVOID, __int64 **, LPVOID *, int *))(*(_QWORD *)ppv + 32LL);
    v59 = -1;
    v60 = -1;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    v18 = v17(v16, v54, &v49, &pv, &v53);
    v15 = v18;
    if ( v18 < 0 )
    {
      v11 = v18 == -2147023728;
LABEL_20:
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v59 = 0;
      v60 = 0;
      v19 = v49;
      if ( v49 )
      {
        v49 = 0;
        (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
      }
      goto LABEL_24;
    }
    v61 = 0;
    v62 = 0;
    v63 = 0;
    v34 = *v49;
    v62 = -1;
    v63 = -1;
    v15 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v34 + 24))(v49, &v61);
    if ( v15 < 0 )
    {
LABEL_86:
      if ( v61 )
        CoTaskMemFree(v61);
      goto LABEL_20;
    }
    v55 = 0;
    v56 = 0;
    v57 = 0;
    v35 = *v49;
    v56 = -1;
    v57 = -1;
    v15 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v35 + 40))(v49, &v55);
    if ( v15 < 0 || (v52 = 0, v15 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v49 + 168))(v49, &v52), v15 < 0) )
    {
LABEL_84:
      if ( v55 )
        CoTaskMemFree(v55);
      goto LABEL_86;
    }
    v51 = 0;
    v36 = pszPath;
    if ( pszPath )
    {
      v42 = v49;
      v43 = *(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))(*v49 + 112);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
      v15 = v43(v42, &GUID_1b317651_e01a_4d23_bcf5_ec4db0fe6c84, &v51);
      if ( v15 < 0 )
      {
LABEL_82:
        v41 = v51;
        if ( v51 )
        {
          v51 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
        }
        goto LABEL_84;
      }
      v36 = pszPath;
    }
    pszPath = 0;
    v15 = (*(__int64 (__fastcall **)(void *, LPVOID, LPVOID, LPWSTR *))(*(_QWORD *)ppv + 136LL))(ppv, v61, pv, &pszPath);
    v37 = pszPath;
    if ( v15 >= 0 )
    {
      PathRemoveBackslashW(pszPath);
      if ( a3 )
      {
        v38 = (unsigned __int16 *)v55;
        v55 = 0;
        v57 = 0;
        v56 = 0;
        *a3 = v38;
      }
      if ( a4 )
      {
        v39 = (unsigned __int16 *)v61;
        v61 = 0;
        v63 = 0;
        v62 = 0;
        *a4 = v39;
      }
      if ( a5 )
        *(_DWORD *)a5 = v52;
      if ( a6 )
        *(_DWORD *)a6 = v53;
      if ( a7 )
      {
        v37 = 0;
        *a7 = pszPath;
      }
      else
      {
        v37 = pszPath;
      }
      if ( a8 )
      {
        v40 = (unsigned __int16 *)pv;
        pv = 0;
        v60 = 0;
        v59 = 0;
        *a8 = v40;
      }
      if ( v36 )
      {
        v44 = v51;
        v51 = 0;
        *(_QWORD *)v36 = v44;
      }
    }
    pszPath = 0;
    CoTaskMemFree(v37);
    goto LABEL_82;
  }
LABEL_26:
  if ( v54 )
    CoTaskMemFree(v54);
  if ( !v11 )
    return (unsigned int)v15;
  v10 = -1;
  v9 = v64;
LABEL_30:
  v21 = 0;
  v22 = 0;
  v23 = L"network";
  if ( !(unsigned int)CFSFolder::_IsNetFolder(v9) )
    v23 = L"computer";
  v24 = -1;
  do
    ++v24;
  while ( v23[v24] );
  v25 = v24 + 1;
  if ( v24 + 1 < v24 || (v64 = 0, !is_mul_ok(v25, 2u)) )
  {
    v28 = -2147024362;
LABEL_46:
    if ( v28 >= 0 )
    {
      v55 = 0;
      v56 = 0;
      v57 = 0;
      if ( v22 == -1 )
      {
        if ( v21 )
        {
          do
            ++v10;
          while ( v21[v10] );
        }
        else
        {
          v10 = 0;
        }
      }
      else
      {
        v10 = v22;
      }
      v28 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              &v55,
              v21,
              v10);
      if ( v28 < 0 )
      {
        v33 = v55;
      }
      else
      {
        if ( a3 )
        {
          v32 = v21;
          v21 = 0;
          *a3 = v32;
        }
        if ( a4 )
        {
          v33 = 0;
          *a4 = v55;
        }
        else
        {
          v33 = v55;
        }
        v28 = 1;
      }
      if ( v33 )
        CoTaskMemFree(v33);
    }
    goto LABEL_47;
  }
  v26 = (wchar_t *)CoTaskMemAlloc(2 * v25);
  v27 = v26;
  if ( v26 )
  {
    v22 = v24;
    v28 = 0;
    v21 = v26;
    *v26 = 0;
    if ( v24 != -1 )
    {
      if ( v25 > 0x7FFFFFFF || v24 > 0x7FFFFFFE )
      {
        *v26 = 0;
      }
      else
      {
        do
        {
          if ( !v24 )
            break;
          v29 = *v23;
          if ( !*v23 )
            break;
          ++v23;
          *v27++ = v29;
          --v24;
          --v25;
        }
        while ( v25 );
        v30 = v27 - 1;
        if ( v25 )
          v30 = v27;
        *v30 = 0;
      }
    }
    goto LABEL_46;
  }
  v28 = -2147024882;
LABEL_47:
  if ( v21 )
    CoTaskMemFree(v21);
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x1800adfc0  push    rbp
0x1800adfc2  push    rbx
0x1800adfc3  push    rsi
0x1800adfc4  push    rdi
0x1800adfc5  push    r12
0x1800adfc7  push    r13
0x1800adfc9  push    r14
0x1800adfcb  push    r15
0x1800adfcd  lea     rbp, [rsp-7]
0x1800adfd2  sub     rsp, 0D8h
0x1800adfd9  mov     rax, cs:__security_cookie
0x1800adfe0  xor     rax, rsp
0x1800adfe3  mov     [rbp+3Fh+var_48], rax
0x1800adfe7  mov     [rsp+110h+var_D8], r9
0x1800adfec  mov     [rsp+110h+var_E0], r8
0x1800adff1  mov     [rbp+3Fh+var_B8], rdx
0x1800adff5  mov     rbx, rcx
0x1800adff8  mov     [rbp+3Fh+var_50], rcx
0x1800adffc  mov     rsi, [rbp+3Fh+arg_20]
0x1800ae000  mov     r14, [rbp+3Fh+arg_28]
0x1800ae004  mov     r12, [rbp+3Fh+arg_30]
0x1800ae008  mov     r15, [rbp+3Fh+arg_38]
0x1800ae00f  mov     rax, [rbp+3Fh+arg_40]
0x1800ae016  mov     [rsp+110h+pszPath], rax
0x1800ae01b  xor     edi, edi
0x1800ae01d  test    r8, r8
0x1800ae020  jz      short loc_1800AE025
0x1800ae022  mov     [r8], rdi
0x1800ae025  test    r9, r9
0x1800ae028  jz      short loc_1800AE02D
0x1800ae02a  mov     [r9], rdi
0x1800ae02d  test    rsi, rsi
0x1800ae030  jz      short loc_1800AE034
0x1800ae032  mov     [rsi], edi
0x1800ae034  test    r14, r14
0x1800ae037  jz      short loc_1800AE03C
0x1800ae039  mov     [r14], edi
0x1800ae03c  test    r12, r12
0x1800ae03f  jz      short loc_1800AE045
0x1800ae041  mov     [r12], rdi
0x1800ae045  test    r15, r15
0x1800ae048  jz      short loc_1800AE04D
0x1800ae04a  mov     [r15], rdi
0x1800ae04d  test    rax, rax
0x1800ae050  jnz     loc_1800AE601
0x1800ae056  mov     [rsp+110h+var_D0], 1
0x1800ae05b  lea     rax, [rsp+110h+var_D0]
0x1800ae060  mov     [rbp+3Fh+var_A0], rax
0x1800ae064  lea     rcx, [rbp+3Fh+var_A0]
0x1800ae068  call    ??R_lambda_ea9c6a719f4a9bb818bf1c421ccbcdfc_@@QEBA@XZ; _lambda_ea9c6a719f4a9bb818bf1c421ccbcdfc_::operator()(void)
0x1800ae06d  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1800ae074  cmp     [rsp+110h+var_D0], dil
0x1800ae079  jz      loc_1800AE1FD
0x1800ae07f  xor     r13b, r13b
0x1800ae082  mov     [rbp+3Fh+var_A0], rdi
0x1800ae086  lea     rdi, [rbx+138h]
0x1800ae08d  mov     rax, [rdi]
0x1800ae090  mov     rbx, [rax+70h]
0x1800ae094  lea     rcx, [rbp+3Fh+var_A0]
0x1800ae098  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800ae09d  mov     r9, rax
0x1800ae0a0  mov     r8d, 3
0x1800ae0a6  mov     rdx, [rbp+3Fh+var_B8]
0x1800ae0aa  mov     rcx, rdi
0x1800ae0ad  mov     rax, rbx
0x1800ae0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae0b5  mov     edi, eax
0x1800ae0b7  test    eax, eax
0x1800ae0b9  js      loc_1800AE1D2
0x1800ae0bf  xor     ebx, ebx
0x1800ae0c1  mov     [rbp+3Fh+var_B8], rbx
0x1800ae0c5  lea     rcx, [rbp+3Fh+var_B8]
0x1800ae0c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ae0ce  lea     rax, [rbp+3Fh+var_B8]
0x1800ae0d2  mov     [rsp+110h+ppv], rax; ppv
0x1800ae0d7  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x1800ae0de  xor     r8d, r8d; pUnkOuter
0x1800ae0e1  lea     rdx, CLSID_SyncRootManager; pclsid
0x1800ae0e8  xor     ecx, ecx; pszCLSID
0x1800ae0ea  call    cs:__imp_SHCoCreateInstance
0x1800ae0f1  nop     dword ptr [rax+rax+00h]
0x1800ae0f6  mov     edi, eax
0x1800ae0f8  test    eax, eax
0x1800ae0fa  js      loc_1800AE1B8
0x1800ae100  mov     [rsp+110h+var_C0], rbx
0x1800ae105  mov     [rbp+3Fh+var_A4], ebx
0x1800ae108  mov     [rbp+3Fh+pv], rbx
0x1800ae10c  mov     [rbp+3Fh+var_78], rbx
0x1800ae110  mov     [rbp+3Fh+var_70], rbx
0x1800ae114  mov     rdi, [rbp+3Fh+var_B8]
0x1800ae118  mov     rax, [rdi]
0x1800ae11b  mov     rbx, [rax+20h]
0x1800ae11f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800ae126  mov     [rbp+3Fh+var_78], rax
0x1800ae12a  mov     [rbp+3Fh+var_70], rax
0x1800ae12e  lea     rcx, [rsp+110h+var_C0]
0x1800ae133  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ae138  lea     rax, [rbp+3Fh+var_A4]
0x1800ae13c  mov     [rsp+110h+ppv], rax
0x1800ae141  lea     r9, [rbp+3Fh+pv]
0x1800ae145  lea     r8, [rsp+110h+var_C0]
0x1800ae14a  mov     rdx, [rbp+3Fh+var_A0]
0x1800ae14e  mov     rcx, rdi
0x1800ae151  mov     rax, rbx
0x1800ae154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae159  mov     edi, eax
0x1800ae15b  test    eax, eax
0x1800ae15d  jns     loc_1800AE3B0
0x1800ae163  movzx   r13d, r13b
0x1800ae167  cmp     eax, 80070490h
0x1800ae16c  mov     eax, 1
0x1800ae171  cmovz   r13d, eax
0x1800ae175  mov     rcx, [rbp+3Fh+pv]; pv
0x1800ae179  test    rcx, rcx
0x1800ae17c  jz      loc_1800AE58F
0x1800ae182  call    cs:__imp_CoTaskMemFree
0x1800ae189  nop     dword ptr [rax+rax+00h]
0x1800ae18e  xor     ebx, ebx
0x1800ae190  mov     [rbp+3Fh+pv], rbx
0x1800ae194  mov     [rbp+3Fh+var_78], rbx
0x1800ae198  mov     [rbp+3Fh+var_70], rbx
0x1800ae19c  mov     rcx, [rsp+110h+var_C0]
0x1800ae1a1  test    rcx, rcx
0x1800ae1a4  jz      short loc_1800AE1B8
0x1800ae1a6  mov     [rsp+110h+var_C0], rbx
0x1800ae1ab  mov     rax, [rcx]
0x1800ae1ae  mov     rax, [rax+10h]
0x1800ae1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae1b7  nop
0x1800ae1b8  mov     rcx, [rbp+3Fh+var_B8]
0x1800ae1bc  test    rcx, rcx
0x1800ae1bf  jz      short loc_1800AE1D2
0x1800ae1c1  mov     [rbp+3Fh+var_B8], rbx
0x1800ae1c5  mov     rax, [rcx]
0x1800ae1c8  mov     rax, [rax+10h]
0x1800ae1cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae1d1  nop
0x1800ae1d2  mov     rcx, [rbp+3Fh+var_A0]; pv
0x1800ae1d6  test    rcx, rcx
0x1800ae1d9  jz      short loc_1800AE1E7
0x1800ae1db  call    cs:__imp_CoTaskMemFree
0x1800ae1e2  nop     dword ptr [rax+rax+00h]
0x1800ae1e7  test    r13b, r13b
0x1800ae1ea  jz      loc_1800AE588
0x1800ae1f0  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1800ae1f7  mov     rbx, [rbp+3Fh+var_50]
0x1800ae1fb  xor     edi, edi
0x1800ae1fd  mov     r15, rdi
0x1800ae200  mov     r12, rdi
0x1800ae203  mov     rcx, rbx; this
0x1800ae206  call    ?_IsNetFolder@CFSFolder@@IEAAHXZ; CFSFolder::_IsNetFolder(void)
0x1800ae20b  lea     rcx, aComputer; "computer"
0x1800ae212  lea     rdi, aNetwork; "network"
0x1800ae219  test    eax, eax
0x1800ae21b  cmovz   rdi, rcx
0x1800ae21f  mov     rbx, r13
0x1800ae222  inc     rbx
0x1800ae225  cmp     word ptr [rdi+rbx*2], 0
0x1800ae22a  jnz     short loc_1800AE222
0x1800ae22c  lea     rsi, [rbx+1]
0x1800ae230  cmp     rsi, rbx
0x1800ae233  jb      loc_1800AE30E
0x1800ae239  mov     [rbp+3Fh+var_50], 0
0x1800ae241  mov     eax, 2
0x1800ae246  mul     rsi
0x1800ae249  test    rdx, rdx
0x1800ae24c  jnz     loc_1800AE30E
0x1800ae252  mov     rcx, rax; cb
0x1800ae255  call    cs:__imp_CoTaskMemAlloc
0x1800ae25c  nop     dword ptr [rax+rax+00h]
0x1800ae261  mov     rdx, rax
0x1800ae264  test    rax, rax
0x1800ae267  jz      loc_1800AE596
0x1800ae26d  mov     r12, rbx
0x1800ae270  xor     r14d, r14d
0x1800ae273  mov     r15, rax
0x1800ae276  xor     ecx, ecx
0x1800ae278  mov     [rax], cx
0x1800ae27b  test    rsi, rsi
0x1800ae27e  jz      short loc_1800AE2D1
0x1800ae280  cmp     rsi, 7FFFFFFFh
0x1800ae287  ja      loc_1800AE619
0x1800ae28d  cmp     rbx, 7FFFFFFEh
0x1800ae294  ja      loc_1800AE619
0x1800ae29a  nop     word ptr [rax+rax+00h]
0x1800ae2a0  test    rbx, rbx
0x1800ae2a3  jz      short loc_1800AE2C1
0x1800ae2a5  movzx   eax, word ptr [rdi]
0x1800ae2a8  test    ax, ax
0x1800ae2ab  jz      short loc_1800AE2C1
0x1800ae2ad  add     rdi, 2
0x1800ae2b1  mov     [rdx], ax
0x1800ae2b4  add     rdx, 2
0x1800ae2b8  dec     rbx
0x1800ae2bb  sub     rsi, 1
0x1800ae2bf  jnz     short loc_1800AE2A0
0x1800ae2c1  lea     rcx, [rdx-2]
0x1800ae2c5  test    rsi, rsi
0x1800ae2c8  cmovnz  rcx, rdx
0x1800ae2cc  xor     eax, eax
0x1800ae2ce  mov     [rcx], ax
0x1800ae2d1  test    r14d, r14d
0x1800ae2d4  jns     short loc_1800AE316
0x1800ae2d6  test    r15, r15
0x1800ae2d9  jz      short loc_1800AE2EA
0x1800ae2db  mov     rcx, r15; pv
0x1800ae2de  call    cs:__imp_CoTaskMemFree
0x1800ae2e5  nop     dword ptr [rax+rax+00h]
0x1800ae2ea  mov     eax, r14d
0x1800ae2ed  mov     rcx, [rbp+3Fh+var_48]
0x1800ae2f1  xor     rcx, rsp; StackCookie
0x1800ae2f4  call    __security_check_cookie
0x1800ae2f9  add     rsp, 0D8h
0x1800ae300  pop     r15
0x1800ae302  pop     r14
0x1800ae304  pop     r13
0x1800ae306  pop     r12
0x1800ae308  pop     rdi
0x1800ae309  pop     rsi
0x1800ae30a  pop     rbx
0x1800ae30b  pop     rbp
0x1800ae30c  retn
0x1800ae30e  mov     r14d, 80070216h
0x1800ae314  jmp     short loc_1800AE2D1
0x1800ae316  mov     [rbp+3Fh+var_98], 0
0x1800ae31e  mov     [rbp+3Fh+var_90], 0
0x1800ae326  mov     [rbp+3Fh+var_88], 0
0x1800ae32e  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x1800ae332  jnz     loc_1800AE62B
0x1800ae338  test    r15, r15
0x1800ae33b  jz      loc_1800AE623
0x1800ae341  inc     r13
0x1800ae344  cmp     word ptr [r15+r13*2], 0
0x1800ae34a  jnz     short loc_1800AE341
0x1800ae34c  mov     r8, r13
0x1800ae34f  mov     rdx, r15
0x1800ae352  lea     rcx, [rbp+3Fh+var_98]
0x1800ae356  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800ae35b  mov     r14d, eax
0x1800ae35e  test    eax, eax
0x1800ae360  js      loc_1800AE633
0x1800ae366  mov     rcx, [rsp+110h+var_E0]
0x1800ae36b  test    rcx, rcx
0x1800ae36e  jz      short loc_1800AE379
0x1800ae370  mov     rax, r15
0x1800ae373  xor     r15d, r15d
0x1800ae376  mov     [rcx], rax
0x1800ae379  mov     rdx, [rsp+110h+var_D8]
0x1800ae37e  test    rdx, rdx
0x1800ae381  jz      loc_1800AE5A1
0x1800ae387  mov     rax, [rbp+3Fh+var_98]
0x1800ae38b  xor     ecx, ecx; pv
0x1800ae38d  mov     [rdx], rax
0x1800ae390  mov     r14d, 1
0x1800ae396  test    rcx, rcx
0x1800ae399  jz      loc_1800AE2D6
0x1800ae39f  call    cs:__imp_CoTaskMemFree
0x1800ae3a6  nop     dword ptr [rax+rax+00h]
0x1800ae3ab  jmp     loc_1800AE2D6
0x1800ae3b0  xor     eax, eax
0x1800ae3b2  mov     [rbp+3Fh+var_68], rax
0x1800ae3b6  mov     [rbp+3Fh+var_60], rax
0x1800ae3ba  mov     [rbp+3Fh+var_58], rax
0x1800ae3be  mov     rcx, [rsp+110h+var_C0]
0x1800ae3c3  mov     rax, [rcx]
0x1800ae3c6  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800ae3cd  mov     [rbp+3Fh+var_60], rbx
0x1800ae3d1  mov     [rbp+3Fh+var_58], rbx
0x1800ae3d5  lea     rdx, [rbp+3Fh+var_68]
0x1800ae3d9  mov     rax, [rax+18h]
0x1800ae3dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae3e2  mov     edi, eax
0x1800ae3e4  test    eax, eax
0x1800ae3e6  js      loc_1800AE56A
0x1800ae3ec  xor     eax, eax
0x1800ae3ee  mov     [rbp+3Fh+var_98], rax
0x1800ae3f2  mov     [rbp+3Fh+var_90], rax
0x1800ae3f6  mov     [rbp+3Fh+var_88], rax
0x1800ae3fa  mov     rcx, [rsp+110h+var_C0]
0x1800ae3ff  mov     rax, [rcx]
0x1800ae402  mov     [rbp+3Fh+var_90], rbx
0x1800ae406  mov     [rbp+3Fh+var_88], rbx
0x1800ae40a  lea     rdx, [rbp+3Fh+var_98]
0x1800ae40e  mov     rax, [rax+28h]
0x1800ae412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae417  mov     edi, eax
0x1800ae419  test    eax, eax
0x1800ae41b  js      loc_1800AE554
0x1800ae421  mov     [rbp+3Fh+var_A8], 0
0x1800ae428  mov     rcx, [rsp+110h+var_C0]
0x1800ae42d  mov     rax, [rcx]
0x1800ae430  lea     rdx, [rbp+3Fh+var_A8]
0x1800ae434  mov     rax, [rax+0A8h]
0x1800ae43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae440  mov     edi, eax
0x1800ae442  test    eax, eax
0x1800ae444  js      loc_1800AE554
0x1800ae44a  mov     [rbp+3Fh+var_B0], 0
0x1800ae452  mov     rbx, [rsp+110h+pszPath]
0x1800ae457  test    rbx, rbx
  ... truncated ...
```
