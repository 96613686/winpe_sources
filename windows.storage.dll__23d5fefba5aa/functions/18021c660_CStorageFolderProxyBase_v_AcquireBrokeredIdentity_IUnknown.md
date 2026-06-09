# CStorageFolderProxyBase::v_AcquireBrokeredIdentity(IUnknown * *)

- ea: `0x18021c660`
- end: `0x18021ccef`
- name: `?v_AcquireBrokeredIdentity@CStorageFolderProxyBase@@MEAAJPEAPEAUIUnknown@@@Z`
- size: `1679`
- prototype: `__int64 __fastcall(CStorageFolderProxyBase *__hidden this, struct IUnknown **)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180009fc0`
- `0x1800118c4`
- `0x180013140`
- `0x18001aecc`
- `0x180020350`
- `0x180038f50`
- `0x18007bbf0`
- `0x18007c1c0`
- `0x18007dcf0`
- `0x18021c660`
- `0x18021ccf8`
- `0x18021cffc`
- `0x18021d0e0`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18021cc6f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18021cc6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021c993`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021ca28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021caba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021cb50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021c993`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021ca28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021caba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021cb50`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18021c8d1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18021c8d1`
- `PROPSYS!PropVariantToBuffer` at `0x18021c85b`
- `PROPSYS!PropVariantToBuffer` at `0x18021c85b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021c6ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021c6ea`

## string_xrefs

- `0x18021c875`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021c9f4`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021ca86`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021cb34`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021cbae`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021cc11`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021cc8a`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021cca2`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x180673824`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021c695`: `v_AcquireBrokeredIdentity`
- `0x18021c6e3`: `Windows.Storage.StorageFolderStaticsBrokered`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CStorageFolderProxyBase::v_AcquireBrokeredIdentity(
        CStorageFolderProxyBase *this,
        struct IUnknown **a2)
{
  int v4; // eax
  HRESULT v5; // ebx
  struct Windows::System::IUser *UserRaw; // rdi
  HSTRING v7; // rbx
  int v8; // eax
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v10)(_QWORD, GUID *, _QWORD **); // rdi
  int v11; // eax
  __int64 (__fastcall *v12)(char *, GUID *, __int64 *); // rbx
  int v13; // eax
  int IsMultiUserAware; // eax
  _QWORD *v16; // rdi
  __int64 v17; // rax
  __int64 (__fastcall *v18)(_QWORD *, LPVOID, _BYTE *, int *); // rbx
  void *v19; // rsi
  int v20; // eax
  int v21; // eax
  __int64 v22; // rcx
  _QWORD *v23; // rcx
  __int64 (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v25; // rcx
  _QWORD *v26; // rcx
  __int64 (__fastcall ***v27)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v28; // rcx
  _QWORD *v29; // rcx
  __int64 (__fastcall ***v30)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v33; // rcx
  __int64 (__fastcall ***v34)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v35; // rcx
  __int64 (__fastcall ***v36)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v37; // rdx
  __int64 (__fastcall *v38)(_QWORD *, struct Windows::System::IUser *, LPVOID, _BYTE *); // rbx
  struct Windows::System::IUser *v39; // rax
  int v40; // eax
  int *v41; // [rsp+20h] [rbp-E0h]
  bool v42; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v43[3]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v44; // [rsp+50h] [rbp-B0h] BYREF
  int v45; // [rsp+60h] [rbp-A0h]
  _QWORD *v46; // [rsp+70h] [rbp-90h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, _QWORD **); // [rsp+78h] [rbp-88h] BYREF
  __int64 v48; // [rsp+80h] [rbp-80h] BYREF
  int v49[2]; // [rsp+88h] [rbp-78h] BYREF
  HSTRING string; // [rsp+90h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v52[192]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE pv[592]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+2F8h]

  WinRTStorageTelemetry::WatchCurrentThread(v52, "v_AcquireBrokeredIdentity", 0);
  v4 = CStorageItemProxyBase::_TryAcquireBrokeredArrayIdentity(this, a2);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC85,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v4,
      (int)v41);
    goto LABEL_14;
  }
  if ( *a2 )
  {
LABEL_30:
    v5 = 0;
    goto LABEL_14;
  }
  v47 = 0;
  UserRaw = CStorageItemProxyBase::LazyGetUserRaw(this);
  if ( WindowsCreateStringReference(L"Windows.Storage.StorageFolderStaticsBrokered", 0x2Cu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v7 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  v8 = Windows::Foundation::GetActivationFactoryAsUser<Windows::Storage::IStorageFolderStatics>(v7, UserRaw, &v47);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC8C,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v8,
      (int)v41);
LABEL_71:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    goto LABEL_14;
  }
  v46 = 0;
  v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
  v10 = **v47;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  v11 = v10(v9, &GUID_6ca9bd66_f046_48a3_9a11_992afeb34e2d, &v46);
  v5 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC8F,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v11,
      (int)v41);
    v35 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
    }
    v36 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
    if ( v47 )
    {
      v47 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v36)[2])(v36);
    }
    goto LABEL_14;
  }
  v48 = 0;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v48);
  v12 = *(__int64 (__fastcall **)(char *, GUID *, __int64 *))(*((_QWORD *)this + 18) + 24LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  v13 = v12((char *)this + 144, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v48);
  v5 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC92,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v13,
      (int)v41);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    v33 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v33 + 16LL))(v33);
    }
    v34 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
    if ( v47 )
    {
      v47 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v34)[2])(v34);
    }
    goto LABEL_14;
  }
  v43[0] = 0;
  v43[1] = (LPVOID)-1LL;
  v43[2] = (LPVOID)-1LL;
  v44 = PKEY_FileAPI_Path;
  v45 = 3;
  IsMultiUserAware = wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v48, &v44, v43);
  v5 = IsMultiUserAware;
  if ( IsMultiUserAware < 0 )
  {
    v37 = 3221;
LABEL_69:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v37,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)IsMultiUserAware,
      (int)v41);
LABEL_70:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v43);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    goto LABEL_71;
  }
  memset_0(pv, 0, sizeof(pv));
  LOWORD(string) = 0;
  v44 = PKEY_FileAPI_FindData;
  v45 = 12;
  v5 = (*(__int64 (__fastcall **)(__int64, __int128 *, HSTRING *))(*(_QWORD *)v48 + 40LL))(v48, &v44, &string);
  if ( v5 < 0 )
    goto LABEL_16;
  if ( !(_WORD)string )
  {
    v5 = -2147023728;
LABEL_16:
    memset_0(pv, 0, sizeof(pv));
    goto LABEL_17;
  }
  if ( (_WORD)string == 65 )
  {
    memcpy_s(
      pv,
      0x250u,
      *(const void *const *)&hstringHeader.Reserved.Reserved2[8],
      LODWORD(hstringHeader.Reserved.Reserved1));
    v5 = 0;
  }
  else
  {
    v5 = PropVariantToBuffer((const PROPVARIANT *const)&string, pv, 0x250u);
  }
LABEL_17:
  PropVariantClear((PROPVARIANT *)&string);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC98,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v5,
      (int)v41);
    if ( v43[0] )
      CoTaskMemFree(v43[0]);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    v31 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
    }
    v32 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
    if ( v47 )
    {
      v47 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v32)[2])(v32);
    }
    goto LABEL_14;
  }
  v42 = 0;
  IsMultiUserAware = Windows::Storage::Internal::UserManagerHelpers::IsMultiUserAware(
                       (void *)0xFFFFFFFFFFFFFFFALL,
                       &v42);
  v5 = IsMultiUserAware;
  if ( IsMultiUserAware < 0 )
  {
    v37 = 3227;
    goto LABEL_69;
  }
  *(_QWORD *)v49 = 0;
  v16 = v46;
  v17 = *v46;
  if ( !v42 )
  {
    v18 = *(__int64 (__fastcall **)(_QWORD *, LPVOID, _BYTE *, int *))(v17 + 32);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v49);
    v19 = v43[0];
    v20 = v18(v16, v43[0], pv, v49);
    v5 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCA4,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
        (const char *)(unsigned int)v20,
        (int)v41);
      v25 = *(_QWORD *)v49;
      if ( *(_QWORD *)v49 )
      {
        *(_QWORD *)v49 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      if ( v19 )
        CoTaskMemFree(v19);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      v26 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
      }
      v27 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
      if ( v47 )
      {
        v47 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v27)[2])(v27);
      }
      goto LABEL_14;
    }
    goto LABEL_21;
  }
  v38 = *(__int64 (__fastcall **)(_QWORD *, struct Windows::System::IUser *, LPVOID, _BYTE *))(v17 + 40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v49);
  v39 = CStorageItemProxyBase::LazyGetUserRaw(this);
  v41 = v49;
  v19 = v43[0];
  v40 = v38(v16, v39, v43[0], pv);
  v5 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCA0,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v40,
      (int)v49);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v49);
    goto LABEL_70;
  }
LABEL_21:
  v21 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, struct IUnknown **))v49)(
          *(_QWORD *)v49,
          &GUID_00000000_0000_0000_c000_000000000046,
          a2);
  v5 = v21;
  if ( v21 >= 0 )
  {
    v22 = *(_QWORD *)v49;
    if ( *(_QWORD *)v49 )
    {
      *(_QWORD *)v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    if ( v19 )
      CoTaskMemFree(v19);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    v23 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
    }
    v24 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
    if ( v47 )
    {
      v47 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v24)[2])(v24);
    }
    goto LABEL_30;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCA7,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
    (const char *)(unsigned int)v21,
    (int)v41);
  v28 = *(_QWORD *)v49;
  if ( *(_QWORD *)v49 )
  {
    *(_QWORD *)v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  if ( v19 )
    CoTaskMemFree(v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  v29 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
  }
  v30 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
  if ( v47 )
  {
    v47 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v30)[2])(v30);
  }
LABEL_14:
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v52);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18021c660  mov     [rsp-8+arg_10], rbx
0x18021c665  push    rbp
0x18021c666  push    rsi
0x18021c667  push    rdi
0x18021c668  push    r14
0x18021c66a  push    r15
0x18021c66c  lea     rbp, [rsp-2D0h]
0x18021c674  sub     rsp, 3D0h
0x18021c67b  mov     rax, cs:__security_cookie
0x18021c682  xor     rax, rsp
0x18021c685  mov     [rbp+2F0h+var_30], rax
0x18021c68c  mov     r14, rdx
0x18021c68f  mov     rsi, rcx
0x18021c692  xor     r8d, r8d
0x18021c695  lea     rdx, aVAcquirebroker; "v_AcquireBrokeredIdentity"
0x18021c69c  lea     rcx, [rbp+2F0h+var_340]
0x18021c6a0  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBD_N@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,bool)
0x18021c6a5  nop
0x18021c6a6  mov     rdx, r14; struct IUnknown **
0x18021c6a9  mov     rcx, rsi; this
0x18021c6ac  call    ?_TryAcquireBrokeredArrayIdentity@CStorageItemProxyBase@@IEAAJPEAPEAUIUnknown@@@Z; CStorageItemProxyBase::_TryAcquireBrokeredArrayIdentity(IUnknown * *)
0x18021c6b1  mov     ebx, eax
0x18021c6b3  xor     r15d, r15d
0x18021c6b6  test    eax, eax
0x18021c6b8  js      loc_18021C86B
0x18021c6be  cmp     [r14], r15
0x18021c6c1  jnz     loc_18021C9E2
0x18021c6c7  mov     [rsp+3F0h+var_378], r15
0x18021c6cc  mov     rcx, rsi; this
0x18021c6cf  call    ?LazyGetUserRaw@CStorageItemProxyBase@@IEAAPEAUIUser@System@Windows@@XZ; CStorageItemProxyBase::LazyGetUserRaw(void)
0x18021c6d4  mov     rdi, rax
0x18021c6d7  lea     r9, [rbp+2F0h+string]; string
0x18021c6db  lea     r8, [rbp+2F0h+hstringHeader]; hstringHeader
0x18021c6df  lea     edx, [r15+2Ch]; length
0x18021c6e3  lea     rcx, ?RuntimeClass_Windows_Storage_StorageFolderStaticsBrokered@@3QBGB; "Windows.Storage.StorageFolderStaticsBro"...
0x18021c6ea  call    cs:__imp_WindowsCreateStringReference
0x18021c6f1  nop     dword ptr [rax+rax+00h]
0x18021c6f6  test    eax, eax
0x18021c6f8  js      loc_18021CC60
0x18021c6fe  mov     rbx, [rbp+2F0h+string]
0x18021c702  lea     rcx, [rsp+3F0h+var_378]
0x18021c707  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021c70c  lea     r8, [rsp+3F0h+var_378]
0x18021c711  mov     rdx, rdi
0x18021c714  mov     rcx, rbx
0x18021c717  call    ??$GetActivationFactoryAsUser@UIStorageFolderStatics@Storage@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAUIUser@System@1@PEAPEAUIStorageFolderStatics@Storage@1@@Z; Windows::Foundation::GetActivationFactoryAsUser<Windows::Storage::IStorageFolderStatics>(HSTRING__ *,Windows::System::IUser *,Windows::Storage::IStorageFolderStatics * *)
0x18021c71c  mov     ebx, eax
0x18021c71e  test    eax, eax
0x18021c720  js      loc_18021CC80
0x18021c726  mov     [rsp+3F0h+var_380], r15
0x18021c72b  mov     rbx, [rsp+3F0h+var_378]
0x18021c730  mov     rax, [rbx]
0x18021c733  mov     rdi, [rax]
0x18021c736  lea     rcx, [rsp+3F0h+var_380]
0x18021c73b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021c740  lea     r8, [rsp+3F0h+var_380]
0x18021c745  lea     rdx, _GUID_6ca9bd66_f046_48a3_9a11_992afeb34e2d
0x18021c74c  mov     rcx, rbx
0x18021c74f  mov     rax, rdi
0x18021c752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021c757  mov     ebx, eax
0x18021c759  test    eax, eax
0x18021c75b  js      loc_18021CC07
0x18021c761  mov     [rbp+2F0h+var_370], r15
0x18021c765  lea     rcx, [rbp+2F0h+var_370]
0x18021c769  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18021c76e  nop
0x18021c76f  lea     rdi, [rsi+90h]
0x18021c776  mov     rax, [rdi]
0x18021c779  mov     rbx, [rax+18h]
0x18021c77d  lea     rcx, [rbp+2F0h+var_370]
0x18021c781  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021c786  lea     r8, [rbp+2F0h+var_370]
0x18021c78a  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18021c791  mov     rcx, rdi
0x18021c794  mov     rax, rbx
0x18021c797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021c79c  mov     ebx, eax
0x18021c79e  test    eax, eax
0x18021c7a0  js      loc_18021CBA4
0x18021c7a6  mov     [rsp+3F0h+var_3B8], r15
0x18021c7ab  or      rax, 0FFFFFFFFFFFFFFFFh
0x18021c7af  mov     [rsp+3F0h+var_3B0], rax
0x18021c7b4  mov     [rsp+3F0h+var_3A8], rax
0x18021c7b9  movups  xmm0, cs:PKEY_FileAPI_Path
0x18021c7c0  movaps  [rsp+3F0h+var_3A0], xmm0
0x18021c7c5  mov     eax, cs:dword_18073AB10
0x18021c7cb  mov     [rsp+3F0h+var_390], eax
0x18021c7cf  lea     r8, [rsp+3F0h+var_3B8]
0x18021c7d4  lea     rdx, [rsp+3F0h+var_3A0]
0x18021c7d9  lea     rcx, [rbp+2F0h+var_370]
0x18021c7dd  call    ??$GetString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18021c7e2  mov     ebx, eax
0x18021c7e4  test    eax, eax
0x18021c7e6  js      loc_18021CC9D
0x18021c7ec  mov     edi, 250h
0x18021c7f1  mov     r8d, edi; Size
0x18021c7f4  xor     edx, edx; Val
0x18021c7f6  lea     rcx, [rbp+2F0h+pv]; void *
0x18021c7fa  call    memset_0
0x18021c7ff  movups  xmm0, cs:PKEY_FileAPI_FindData
0x18021c806  mov     ecx, cs:dword_18073ABE8
0x18021c80c  mov     word ptr [rbp+2F0h+string], r15w
0x18021c811  movaps  [rsp+3F0h+var_3A0], xmm0
0x18021c816  mov     [rsp+3F0h+var_390], ecx
0x18021c81a  mov     rcx, [rbp+2F0h+var_370]
0x18021c81e  mov     rax, [rcx]
0x18021c821  lea     r8, [rbp+2F0h+string]
0x18021c825  lea     rdx, [rsp+3F0h+var_3A0]
0x18021c82a  mov     rax, [rax+28h]
0x18021c82e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021c833  mov     ebx, eax
0x18021c835  test    eax, eax
0x18021c837  js      loc_18021C8BE
0x18021c83d  movzx   eax, word ptr [rbp+2F0h+string]
0x18021c841  test    ax, ax
0x18021c844  jz      short loc_18021C8B9
0x18021c846  cmp     ax, 41h ; 'A'
0x18021c84a  jz      loc_18021CB0E
0x18021c850  mov     r8d, edi; cb
0x18021c853  lea     rdx, [rbp+2F0h+pv]; pv
0x18021c857  lea     rcx, [rbp+2F0h+string]; propvar
0x18021c85b  call    cs:__imp_PropVariantToBuffer
0x18021c862  nop     dword ptr [rax+rax+00h]
0x18021c867  mov     ebx, eax
0x18021c869  jmp     short loc_18021C8CD
0x18021c86b  mov     rcx, [rbp+2F8h]; this
0x18021c872  mov     r9d, eax; char *
0x18021c875  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18021c87c  mov     edx, 0C85h; void *
0x18021c881  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021c886  nop
0x18021c887  lea     rcx, [rbp+2F0h+var_340]; this
0x18021c88b  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x18021c890  mov     eax, ebx
0x18021c892  mov     rcx, [rbp+2F0h+var_30]
0x18021c899  xor     rcx, rsp; StackCookie
0x18021c89c  call    __security_check_cookie
0x18021c8a1  mov     rbx, [rsp+3F0h+arg_10]
0x18021c8a9  add     rsp, 3D0h
0x18021c8b0  pop     r15
0x18021c8b2  pop     r14
0x18021c8b4  pop     rdi
0x18021c8b5  pop     rsi
0x18021c8b6  pop     rbp
0x18021c8b7  retn
0x18021c8b9  mov     ebx, 80070490h
0x18021c8be  mov     r8, rdi; Size
0x18021c8c1  xor     edx, edx; Val
0x18021c8c3  lea     rcx, [rbp+2F0h+pv]; void *
0x18021c8c7  call    memset_0
0x18021c8cc  nop
0x18021c8cd  lea     rcx, [rbp+2F0h+string]; pvar
0x18021c8d1  call    cs:__imp_PropVariantClear
0x18021c8d8  nop     dword ptr [rax+rax+00h]
0x18021c8dd  test    ebx, ebx
0x18021c8df  js      loc_18021CB2A
0x18021c8e5  mov     [rsp+3F0h+var_3C0], r15b
0x18021c8ea  lea     rdx, [rsp+3F0h+var_3C0]; bool *
0x18021c8ef  mov     rcx, 0FFFFFFFFFFFFFFFAh; void *
0x18021c8f6  call    ?IsMultiUserAware@UserManagerHelpers@Internal@Storage@Windows@@SAJPEAXPEA_N@Z; Windows::Storage::Internal::UserManagerHelpers::IsMultiUserAware(void *,bool *)
0x18021c8fb  mov     ebx, eax
0x18021c8fd  test    eax, eax
0x18021c8ff  js      loc_18021CCE8
0x18021c905  mov     qword ptr [rbp+2F0h+var_368], r15
0x18021c909  mov     rdi, [rsp+3F0h+var_380]
0x18021c90e  lea     rcx, [rbp+2F0h+var_368]
0x18021c912  mov     rax, [rdi]
0x18021c915  cmp     [rsp+3F0h+var_3C0], r15b
0x18021c91a  jnz     loc_1806737DC
0x18021c920  mov     rbx, [rax+20h]
0x18021c924  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021c929  lea     r9, [rbp+2F0h+var_368]
0x18021c92d  lea     r8, [rbp+2F0h+pv]
0x18021c931  mov     rsi, [rsp+3F0h+var_3B8]
0x18021c936  mov     rdx, rsi
0x18021c939  mov     rcx, rdi
0x18021c93c  mov     rax, rbx
0x18021c93f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021c944  mov     ebx, eax
0x18021c946  test    eax, eax
0x18021c948  js      loc_18021C9EA
0x18021c94e  mov     rcx, qword ptr [rbp+2F0h+var_368]
0x18021c952  mov     rax, [rcx]
0x18021c955  mov     r8, r14
0x18021c958  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18021c95f  mov     rax, [rax]
0x18021c962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021c967  mov     ebx, eax
0x18021c969  test    eax, eax
0x18021c96b  js      loc_18021CA7C
0x18021c971  mov     rcx, qword ptr [rbp+2F0h+var_368]
0x18021c975  test    rcx, rcx
0x18021c978  jz      short loc_18021C98B
0x18021c97a  mov     qword ptr [rbp+2F0h+var_368], r15
0x18021c97e  mov     rax, [rcx]
0x18021c981  mov     rax, [rax+10h]
0x18021c985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021c98a  nop
0x18021c98b  test    rsi, rsi
0x18021c98e  jz      short loc_18021C9A0
0x18021c990  mov     rcx, rsi; pv
0x18021c993  call    cs:__imp_CoTaskMemFree
0x18021c99a  nop     dword ptr [rax+rax+00h]
0x18021c99f  nop
0x18021c9a0  lea     rcx, [rbp+2F0h+var_370]
0x18021c9a4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021c9a9  nop
0x18021c9aa  mov     rcx, [rsp+3F0h+var_380]
0x18021c9af  test    rcx, rcx
0x18021c9b2  jz      short loc_18021C9C6
0x18021c9b4  mov     [rsp+3F0h+var_380], r15
0x18021c9b9  mov     rax, [rcx]
0x18021c9bc  mov     rax, [rax+10h]
0x18021c9c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021c9c5  nop
0x18021c9c6  mov     rcx, [rsp+3F0h+var_378]
0x18021c9cb  test    rcx, rcx
0x18021c9ce  jz      short loc_18021C9E2
0x18021c9d0  mov     [rsp+3F0h+var_378], r15
0x18021c9d5  mov     rax, [rcx]
0x18021c9d8  mov     rax, [rax+10h]
0x18021c9dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021c9e1  nop
0x18021c9e2  mov     ebx, r15d
0x18021c9e5  jmp     loc_18021C887
0x18021c9ea  mov     rcx, [rbp+2F8h]; this
0x18021c9f1  mov     r9d, eax; char *
0x18021c9f4  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18021c9fb  mov     edx, 0CA4h; void *
0x18021ca00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021ca05  nop
0x18021ca06  mov     rcx, qword ptr [rbp+2F0h+var_368]
0x18021ca0a  test    rcx, rcx
0x18021ca0d  jz      short loc_18021CA20
0x18021ca0f  mov     qword ptr [rbp+2F0h+var_368], r15
0x18021ca13  mov     rax, [rcx]
0x18021ca16  mov     rax, [rax+10h]
0x18021ca1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021ca1f  nop
0x18021ca20  test    rsi, rsi
0x18021ca23  jz      short loc_18021CA35
0x18021ca25  mov     rcx, rsi; pv
0x18021ca28  call    cs:__imp_CoTaskMemFree
0x18021ca2f  nop     dword ptr [rax+rax+00h]
0x18021ca34  nop
0x18021ca35  lea     rcx, [rbp+2F0h+var_370]
0x18021ca39  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021ca3e  nop
0x18021ca3f  mov     rcx, [rsp+3F0h+var_380]
0x18021ca44  test    rcx, rcx
0x18021ca47  jz      short loc_18021CA5B
0x18021ca49  mov     [rsp+3F0h+var_380], r15
0x18021ca4e  mov     rax, [rcx]
0x18021ca51  mov     rax, [rax+10h]
0x18021ca55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021ca5a  nop
0x18021ca5b  mov     rcx, [rsp+3F0h+var_378]
0x18021ca60  test    rcx, rcx
0x18021ca63  jz      short loc_18021CA77
0x18021ca65  mov     [rsp+3F0h+var_378], r15
0x18021ca6a  mov     rax, [rcx]
0x18021ca6d  mov     rax, [rax+10h]
0x18021ca71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021ca76  nop
0x18021ca77  jmp     loc_18021C887
0x18021ca7c  mov     rcx, [rbp+2F8h]; this
0x18021ca83  mov     r9d, eax; char *
0x18021ca86  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18021ca8d  mov     edx, 0CA7h; void *
0x18021ca92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021ca97  nop
0x18021ca98  mov     rcx, qword ptr [rbp+2F0h+var_368]
0x18021ca9c  test    rcx, rcx
0x18021ca9f  jz      short loc_18021CAB2
0x18021caa1  mov     qword ptr [rbp+2F0h+var_368], r15
0x18021caa5  mov     rax, [rcx]
0x18021caa8  mov     rax, [rax+10h]
0x18021caac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021cab1  nop
0x18021cab2  test    rsi, rsi
0x18021cab5  jz      short loc_18021CAC7
0x18021cab7  mov     rcx, rsi; pv
0x18021caba  call    cs:__imp_CoTaskMemFree
0x18021cac1  nop     dword ptr [rax+rax+00h]
0x18021cac6  nop
0x18021cac7  lea     rcx, [rbp+2F0h+var_370]
0x18021cacb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021cad0  nop
0x18021cad1  mov     rcx, [rsp+3F0h+var_380]
0x18021cad6  test    rcx, rcx
0x18021cad9  jz      short loc_18021CAED
0x18021cadb  mov     [rsp+3F0h+var_380], r15
0x18021cae0  mov     rax, [rcx]
0x18021cae3  mov     rax, [rax+10h]
0x18021cae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021caec  nop
0x18021caed  mov     rcx, [rsp+3F0h+var_378]
0x18021caf2  test    rcx, rcx
0x18021caf5  jz      short loc_18021CB09
  ... truncated ...
```
