# CUserTileStore::_SetImagesOnUserManagerAndCache(IStream *,IStream *,IStream *,IStream *,ushort const *)

- ea: `0x18003b9c4`
- end: `0x18003c29b`
- name: `?_SetImagesOnUserManagerAndCache@CUserTileStore@@AEAAJPEAUIStream@@000PEBG@Z`
- size: `2263`
- prototype: `int(CUserTileStore *__hidden this, struct IStream *, struct IStream *, struct IStream *, struct IStream *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003b82c`

## callees

- `0x18000c410`
- `0x180014e10`
- `0x180023ec0`
- `0x18002d0d0`
- `0x18002e93c`
- `0x18003729c`
- `0x18003b804`
- `0x18003b9c4`
- `0x18003c2a4`
- `0x18003c7a4`
- `0x18003cbb8`
- `0x18003cc5c`
- `0x180049800`
- `0x180049824`
- `0x18004cca8`
- `0x180052a5c`
- `0x180054130`
- `0x1800b1214`
- `0x1800cc054`
- `0x1800cd274`
- `0x1800db3e8`
- `0x1800ed010`

## import_xrefs

- `ntdll!WinSqmSetDWORD` at `0x18003c16f`
- `ntdll!WinSqmSetDWORD` at `0x18003c16f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x18003c0aa`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x18003c0aa`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x18003bdbc`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x18003bdbc`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x18003c0cb`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x18003c0cb`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18003ba59`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18003ba59`
- `SHELL32!__imp_SHSetUserPicturePath` at `0x18003c1d9`
- `SHELL32!__imp_SHSetUserPicturePath` at `0x18003c1d9`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003bafc`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003bafc`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003bab4`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003bab4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003bc96`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003bc96`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall CUserTileStore::_SetImagesOnUserManagerAndCache(
        CUserTileStore *this,
        struct IStream *a2,
        struct IStream *a3,
        struct IStream *a4,
        struct IStream *a5,
        unsigned __int16 *a6)
{
  char *v10; // r14
  LPOLESTR *v11; // rdi
  unsigned int v12; // ebx
  HRESULT v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  _QWORD **v18; // rax
  _QWORD *v19; // rbx
  LPVOID v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  struct IStream *v23; // rcx
  HRESULT v24; // eax
  __int64 v25; // rcx
  LPVOID v26; // rbx
  __int64 (__fastcall *v27)(LPVOID, _QWORD, _QWORD, struct IStream *); // r14
  struct IStream *v28; // rdx
  int v29; // eax
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  const WCHAR *v33; // rbx
  unsigned __int64 v34; // rcx
  int v35; // eax
  int v36; // edx
  unsigned int v37; // r8d
  unsigned int v38; // eax
  int v39; // r8d
  __int64 *v40; // rax
  __int64 v41; // rbx
  LPVOID v42; // rcx
  int v43; // eax
  int v44; // eax
  int v45; // eax
  void *v46; // rdx
  unsigned int v47; // r8d
  __int64 (*v48)(void); // rbx
  const char *v49; // r9
  __int64 (*v50)(void); // rax
  int v51; // eax
  struct IStream *v52; // rcx
  unsigned int v53; // edx
  HRESULT TilePath; // eax
  int v55; // eax
  int *ppv; // [rsp+20h] [rbp-148h]
  int ppva; // [rsp+20h] [rbp-148h]
  int ppvb; // [rsp+20h] [rbp-148h]
  int ppvc; // [rsp+20h] [rbp-148h]
  char v60[8]; // [rsp+40h] [rbp-128h] BYREF
  unsigned int v61[2]; // [rsp+48h] [rbp-120h] BYREF
  LPVOID v62; // [rsp+50h] [rbp-118h] BYREF
  int v63[2]; // [rsp+58h] [rbp-110h] BYREF
  __int64 v64; // [rsp+60h] [rbp-108h] BYREF
  struct IStream *v65; // [rsp+68h] [rbp-100h] BYREF
  char *v66; // [rsp+70h] [rbp-F8h] BYREF
  LPWSTR v67; // [rsp+78h] [rbp-F0h] BYREF
  __int64 v68; // [rsp+80h] [rbp-E8h] BYREF
  __int64 v69; // [rsp+88h] [rbp-E0h] BYREF
  __int64 v70; // [rsp+90h] [rbp-D8h] BYREF
  LPWSTR v71; // [rsp+98h] [rbp-D0h] BYREF
  __int64 v72; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 v73; // [rsp+A8h] [rbp-C0h] BYREF
  __int64 v74; // [rsp+B0h] [rbp-B8h] BYREF
  __int64 *v75; // [rsp+B8h] [rbp-B0h] BYREF
  __int64 *v76; // [rsp+C0h] [rbp-A8h] BYREF
  int v77[2]; // [rsp+C8h] [rbp-A0h] BYREF
  _QWORD *v78; // [rsp+D0h] [rbp-98h] BYREF
  unsigned __int16 *v79; // [rsp+D8h] [rbp-90h]
  __int64 *v80; // [rsp+E0h] [rbp-88h]
  char v81; // [rsp+E8h] [rbp-80h]
  GUID pguid; // [rsp+F0h] [rbp-78h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+100h] [rbp-68h] BYREF
  __int64 v84; // [rsp+118h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v79 = a6;
  v10 = (char *)this + 48;
  *((_BYTE *)this + 48) = 0;
  v11 = (LPOLESTR *)((char *)this + 40);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    (char *)this + 40,
    0);
  if ( !a2 && !a3 && !a4 )
  {
    v12 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x559,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
      (const char *)0x80070057LL,
      (int)ppv);
    return v12;
  }
  if ( (unsigned int)SHWindowsPolicy(POLID_UseDefaultTile) )
    return 2147500037LL;
  v64 = 0;
  v14 = CoCreateInstanceAsSystem(&CLSID_UserTileBroker, &GUID_d6d737ff_9e13_4a65_be89_a1e013cc6b76, &v64);
  v12 = v14;
  if ( v14 < 0 )
  {
    v15 = 1372;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
      (const char *)(unsigned int)v14,
      (int)ppv);
LABEL_68:
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v64);
    return v12;
  }
  pguid = 0;
  v14 = CoCreateGuid(&pguid);
  v12 = v14;
  if ( v14 < 0 )
  {
    v15 = 1376;
    goto LABEL_12;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v11,
    0);
  v14 = StringFromCLSID(&pguid, v11);
  v12 = v14;
  if ( v14 < 0 )
  {
    v15 = 1377;
    goto LABEL_12;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, LPOLESTR))(*(_QWORD *)v64 + 48LL))(v64, *v11);
  v12 = v14;
  if ( v14 < 0 )
  {
    v15 = 1378;
    goto LABEL_12;
  }
  v80 = &v64;
  v81 = 1;
  try
  {
    wil::GetActivationFactory<Windows::System::IUserStatics>();
    v70 = 0;
    v16 = *v76;
    v70 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v16 + 56))(v76, &v70);
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x56E,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)v17,
        (int)ppv);
    v18 = (_QWORD **)wil::wait_for_completion<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::System::User *>>>(
                       &v62,
                       v70);
    v19 = *v18;
    *v18 = 0;
    v78 = v19;
    v20 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v69 = 0;
    v21 = *v19;
    v69 = 0;
    v22 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64 *))(v21 + 48))(v19, 0, &v69);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x572,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)v22,
        (int)ppv);
    v23 = a3;
    if ( !a3 )
      v23 = a2;
    v65 = v23;
    if ( v23 )
    {
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v23 + 8LL))(v23);
      v23 = v65;
    }
    if ( !v23 )
    {
      v62 = 0;
      v24 = CoCreateInstance(&CLSID_UserTileValidator, 0, 1u, &GUID_0406e498_0916_49c2_a1c4_10db7bf76766, &v62);
      if ( v24 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x57D,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
          (const char *)(unsigned int)v24,
          ppva);
      v25 = 0;
      *(_QWORD *)v63 = 0;
      *(_QWORD *)v61 = 0;
      v26 = v62;
      v27 = *(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, struct IStream *))(*(_QWORD *)v62 + 24LL);
      *(_QWORD *)v61 = 0;
      v28 = v65;
      v65 = 0;
      if ( v28 )
      {
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v28 + 16LL))(v28);
        v25 = *(_QWORD *)v63;
      }
      *(_QWORD *)v63 = 0;
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      ppv = v63;
      v29 = v27(v26, 0, 0, a4);
      if ( v29 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x57F,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
          (const char *)(unsigned int)v29,
          (int)v63);
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(v61);
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(v63);
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v62);
      v23 = v65;
      v10 = (char *)this + 48;
    }
    v72 = 0;
    v30 = CreateRandomAccessStreamOverStream(v23, 0, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, &v72);
    if ( v30 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x584,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)v30,
        (int)ppv);
    wil::GetActivationFactory<Windows::Storage::Streams::IRandomAccessStreamReferenceStatics>(&v75);
    v68 = 0;
    v31 = *v75;
    v68 = 0;
    v32 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v31 + 64))(v75, v72, &v68);
    if ( v32 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x587,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)v32,
        (int)ppv);
    v63[0] = *((_DWORD *)this + 8);
    wil::GetActivationFactory<Windows::System::Internal::IUserManagerStatics6>(&v74);
    v33 = *v11;
    v84 = 0;
    v61[0] = 0;
    v34 = -1;
    do
      ++v34;
    while ( v33[v34] );
    v35 = ULongLongToULong(v34, v61);
    if ( v35 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v35, v36, v37);
      __debugbreak();
    }
    v38 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v61[0]);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v33, v38, v61[0]);
    *(_QWORD *)v61 = v84;
    *(_QWORD *)v77 = v68;
    v73 = v69;
    v40 = (__int64 *)___call_and_wait_for_completion_UIUserManagerStatics6_Internal_System_Windows__PEAUIUser_34_PEAUIRandomAccessStreamReference_Streams_Storage_4_IPEAUHSTRING____PEAPEAU__IAsyncOperation_PEAVSetPictureResult_Internal_System_Windows___Foundation_4___ZPEAU534_PEAU6784_AEAIPEAU9__wil__YA_A_PPEAUIUserManagerStatics6_Internal_System_Windows__P81234_EAAJPEAUIUser_34_PEAUIRandomAccessStreamReference_Streams_Storage_4_IPEAUHSTRING____PEAPEAU__IAsyncOperation_PEAVSetPictureResult_Internal_System_Windows___Foundation_4__Z__QEAPEAU534___QEAPEAU6784_AEAI__QEAPEAU9__Z(
                       (unsigned int)&v62,
                       v74,
                       v39,
                       (unsigned int)&v73,
                       (__int64)v77,
                       (__int64)v63,
                       (__int64)v61);
    v41 = *v40;
    *v40 = 0;
    v73 = v41;
    v42 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v42 + 16LL))(v42);
    }
    v84 = 0;
    LODWORD(v66) = 0;
    v60[0] = 0;
    v43 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v41 + 48LL))(v41, &v66);
    if ( v43 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x598,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)v43,
        ppvb);
    v44 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v41 + 64LL))(v41, v10);
    if ( v44 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x599,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)v44,
        ppvb);
    v45 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v41 + 72LL))(v41, v60);
    if ( v45 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x59A,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)v45,
        ppvb);
    if ( (int)v66 < 0 && !v60[0] )
      wil::details::in1diag3::Throw_Hr(retaddr, v46, v47, (const char *)(unsigned int)v66, ppvb);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v73);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v74);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v68);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v75);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v72);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v65);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v69);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v78);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v70);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v76);
    v81 = 0;
    IStream_Reset(a3);
    v48 = *(__int64 (**)(void))(*(_QWORD *)v64 + 24LL);
    ppvc = GetScaleFactorForDevice(1);
    v49 = (const char *)a4;
    v50 = v48;
  }
  catch ( ... )
  {
    v63[0] = wil::details::in1diag3::Return_CaughtException(
               retaddr,
               (void *)0x5A1,
               (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
               v49);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 56LL))(v64);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v64);
    return (unsigned int)v63[0];
  }
  v51 = v50();
  v12 = v51;
  if ( v51 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A7,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
      (const char *)(unsigned int)v51,
      ppvc);
    goto LABEL_68;
  }
  _AddUserTileToHistory(v52);
  v71 = 0;
  v53 = (_GetTilePath(2u, 0, 0, &v71) >> 31) + 3;
  if ( a2 && a3 && a4 )
    v53 = 4;
  SQMSetDWORDStreamDataPointWithAppID(0x2141u, v53, v79);
  WinSqmSetDWORD(0, 10451, 1);
  v67 = 0;
  TilePath = _GetTilePath(1u, 0, 0, &v67);
  v12 = TilePath;
  if ( TilePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B1,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
      (const char *)(unsigned int)TilePath,
      ppvc);
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v67);
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v71);
    goto LABEL_68;
  }
  v55 = SHSetUserPicturePath(0, 0, v67);
  v12 = v55;
  if ( v55 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B2,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
      (const char *)(unsigned int)v55,
      ppvc);
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v67);
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v71);
    goto LABEL_68;
  }
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v67);
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v71);
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v64);
  return 0;
}

```

## disassembly

```asm
0x18003b9c4  push    rbx
0x18003b9c6  push    rsi
0x18003b9c7  push    rdi
0x18003b9c8  push    r12
0x18003b9ca  push    r13
0x18003b9cc  push    r14
0x18003b9ce  push    r15
0x18003b9d0  sub     rsp, 130h
0x18003b9d7  mov     rax, cs:__security_cookie
0x18003b9de  xor     rax, rsp
0x18003b9e1  mov     [rsp+168h+var_48], rax
0x18003b9e9  mov     r12, r9
0x18003b9ec  mov     rsi, r8
0x18003b9ef  mov     r13, rdx
0x18003b9f2  mov     r15, rcx
0x18003b9f5  mov     rax, [rsp+168h+arg_28]
0x18003b9fd  mov     [rsp+168h+var_90], rax
0x18003ba05  lea     r14, [rcx+30h]
0x18003ba09  mov     byte ptr [r14], 0
0x18003ba0d  lea     rdi, [rcx+28h]
0x18003ba11  xor     edx, edx
0x18003ba13  mov     rcx, rdi
0x18003ba16  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003ba1b  test    r13, r13
0x18003ba1e  jnz     short loc_18003BA52
0x18003ba20  test    rsi, rsi
0x18003ba23  jnz     short loc_18003BA52
0x18003ba25  test    r12, r12
0x18003ba28  jnz     short loc_18003BA52
0x18003ba2a  mov     rcx, [rsp+168h]; this
0x18003ba32  mov     ebx, 80070057h
0x18003ba37  mov     r9d, ebx; char *
0x18003ba3a  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18003ba41  mov     edx, 559h; void *
0x18003ba46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ba4b  mov     eax, ebx
0x18003ba4d  jmp     loc_18003C277
0x18003ba52  lea     rcx, POLID_UseDefaultTile
0x18003ba59  call    cs:__imp_SHWindowsPolicy
0x18003ba60  nop     dword ptr [rax+rax+00h]
0x18003ba65  test    eax, eax
0x18003ba67  jz      short loc_18003BA73
0x18003ba69  mov     eax, 80004005h
0x18003ba6e  jmp     loc_18003C277
0x18003ba73  mov     [rsp+168h+var_108], 0
0x18003ba7c  lea     r8, [rsp+168h+var_108]
0x18003ba81  lea     rdx, _GUID_d6d737ff_9e13_4a65_be89_a1e013cc6b76
0x18003ba88  lea     rcx, CLSID_UserTileBroker
0x18003ba8f  call    CoCreateInstanceAsSystem
0x18003ba94  mov     ebx, eax
0x18003ba96  test    eax, eax
0x18003ba98  jns     short loc_18003BAA1
0x18003ba9a  mov     edx, 55Ch
0x18003ba9f  jmp     short loc_18003BACB
0x18003baa1  xorps   xmm0, xmm0
0x18003baa4  movups  xmmword ptr [rsp+168h+pguid.Data1], xmm0
0x18003baac  lea     rcx, [rsp+168h+pguid]; pguid
0x18003bab4  call    cs:__imp_CoCreateGuid
0x18003babb  nop     dword ptr [rax+rax+00h]
0x18003bac0  mov     ebx, eax
0x18003bac2  test    eax, eax
0x18003bac4  jns     short loc_18003BAE7
0x18003bac6  mov     edx, 560h; void *
0x18003bacb  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18003bad2  mov     r9d, eax; char *
0x18003bad5  mov     rcx, [rsp+168h]; this
0x18003badd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bae2  jmp     loc_18003C221
0x18003bae7  xor     edx, edx
0x18003bae9  mov     rcx, rdi
0x18003baec  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003baf1  mov     rdx, rdi; lplpsz
0x18003baf4  lea     rcx, [rsp+168h+pguid]; rclsid
0x18003bafc  call    cs:__imp_StringFromCLSID
0x18003bb03  nop     dword ptr [rax+rax+00h]
0x18003bb08  mov     ebx, eax
0x18003bb0a  test    eax, eax
0x18003bb0c  jns     short loc_18003BB15
0x18003bb0e  mov     edx, 561h
0x18003bb13  jmp     short loc_18003BACB
0x18003bb15  mov     rcx, [rsp+168h+var_108]
0x18003bb1a  mov     rax, [rcx]
0x18003bb1d  mov     rdx, [rdi]
0x18003bb20  mov     rax, [rax+30h]
0x18003bb24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb29  mov     ebx, eax
0x18003bb2b  test    eax, eax
0x18003bb2d  jns     short loc_18003BB36
0x18003bb2f  mov     edx, 562h
0x18003bb34  jmp     short loc_18003BACB
0x18003bb36  lea     rax, [rsp+168h+var_108]
0x18003bb3b  mov     [rsp+168h+var_88], rax
0x18003bb43  mov     [rsp+168h+var_80], 1
0x18003bb4b  lea     rcx, [rsp+168h+var_A8]
0x18003bb53  call    ??$GetActivationFactory@UIUserStatics@System@Windows@@@wil@@YA?AV?$com_ptr_t@UIUserStatics@System@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::System::IUserStatics>(ushort const *)
0x18003bb58  nop
0x18003bb59  mov     [rsp+168h+var_D8], 0
0x18003bb65  mov     rcx, [rsp+168h+var_A8]
0x18003bb6d  mov     rax, [rcx]
0x18003bb70  mov     [rsp+168h+var_D8], 0
0x18003bb7c  lea     rdx, [rsp+168h+var_D8]
0x18003bb84  mov     rax, [rax+38h]
0x18003bb88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb8d  mov     rcx, [rsp+168h]; this
0x18003bb95  test    eax, eax
0x18003bb97  jns     short loc_18003BBAD
0x18003bb99  mov     r9d, eax; char *
0x18003bb9c  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18003bba3  mov     edx, 56Eh; void *
0x18003bba8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003bbad  mov     rdx, [rsp+168h+var_D8]
0x18003bbb5  lea     rcx, [rsp+168h+var_118]
0x18003bbba  call    ??$wait_for_completion@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@V?$ComPtr@U?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@U?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::System::User *>>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS)
0x18003bbbf  mov     rbx, [rax]
0x18003bbc2  mov     qword ptr [rax], 0
0x18003bbc9  mov     [rsp+168h+var_98], rbx
0x18003bbd1  mov     rcx, [rsp+168h+var_118]
0x18003bbd6  test    rcx, rcx
0x18003bbd9  jz      short loc_18003BBF1
0x18003bbdb  mov     [rsp+168h+var_118], 0
0x18003bbe4  mov     rax, [rcx]
0x18003bbe7  mov     rax, [rax+10h]
0x18003bbeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbf0  nop
0x18003bbf1  mov     [rsp+168h+var_E0], 0
0x18003bbfd  mov     rax, [rbx]
0x18003bc00  mov     [rsp+168h+var_E0], 0
0x18003bc0c  lea     r8, [rsp+168h+var_E0]
0x18003bc14  xor     edx, edx
0x18003bc16  mov     rcx, rbx
0x18003bc19  mov     rax, [rax+30h]
0x18003bc1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc22  mov     rcx, [rsp+168h]; this
0x18003bc2a  xor     ebx, ebx
0x18003bc2c  test    eax, eax
0x18003bc2e  jns     short loc_18003BC45
0x18003bc30  mov     r9d, eax; char *
0x18003bc33  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18003bc3a  mov     edx, 572h; void *
0x18003bc3f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003bc45  mov     rcx, rsi
0x18003bc48  test    rsi, rsi
0x18003bc4b  cmovz   rcx, r13
0x18003bc4f  mov     [rsp+168h+var_100], rcx
0x18003bc54  test    rcx, rcx
0x18003bc57  jz      short loc_18003BC6A
0x18003bc59  mov     rax, [rcx]
0x18003bc5c  mov     rax, [rax+8]
0x18003bc60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc65  mov     rcx, [rsp+168h+var_100]
0x18003bc6a  test    rcx, rcx
0x18003bc6d  jnz     loc_18003BDA3
0x18003bc73  mov     [rsp+168h+var_118], rbx
0x18003bc78  lea     rax, [rsp+168h+var_118]
0x18003bc7d  mov     [rsp+168h+ppv], rax; int
0x18003bc82  lea     r9, _GUID_0406e498_0916_49c2_a1c4_10db7bf76766; riid
0x18003bc89  xor     edx, edx; pUnkOuter
0x18003bc8b  lea     r8d, [rcx+1]; dwClsContext
0x18003bc8f  lea     rcx, CLSID_UserTileValidator; rclsid
0x18003bc96  call    cs:__imp_CoCreateInstance
0x18003bc9d  nop     dword ptr [rax+rax+00h]
0x18003bca2  mov     rcx, [rsp+168h]; this
0x18003bcaa  test    eax, eax
0x18003bcac  jns     short loc_18003BCC2
0x18003bcae  mov     r9d, eax; char *
0x18003bcb1  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18003bcb8  mov     edx, 57Dh; void *
0x18003bcbd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003bcc2  mov     rcx, rbx
0x18003bcc5  mov     qword ptr [rsp+168h+var_110], rbx
0x18003bcca  mov     qword ptr [rsp+168h+var_120], rbx
0x18003bccf  mov     rbx, [rsp+168h+var_118]
0x18003bcd4  mov     rax, [rbx]
0x18003bcd7  mov     r14, [rax+18h]
0x18003bcdb  mov     qword ptr [rsp+168h+var_120], 0
0x18003bce4  mov     rdx, [rsp+168h+var_100]
0x18003bce9  mov     [rsp+168h+var_100], 0
0x18003bcf2  test    rdx, rdx
0x18003bcf5  jz      short loc_18003BD0B
0x18003bcf7  mov     rax, [rdx]
0x18003bcfa  mov     rcx, rdx
0x18003bcfd  mov     rax, [rax+10h]
0x18003bd01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd06  mov     rcx, qword ptr [rsp+168h+var_110]
0x18003bd0b  mov     qword ptr [rsp+168h+var_110], 0
0x18003bd14  test    rcx, rcx
0x18003bd17  jz      short loc_18003BD26
0x18003bd19  mov     rax, [rcx]
0x18003bd1c  mov     rax, [rax+10h]
0x18003bd20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd25  nop
0x18003bd26  lea     rax, [rsp+168h+var_120]
0x18003bd2b  mov     [rsp+168h+var_138], rax
0x18003bd30  lea     rax, [rsp+168h+var_100]
0x18003bd35  mov     [rsp+168h+var_140], rax
0x18003bd3a  lea     rax, [rsp+168h+var_110]
0x18003bd3f  mov     [rsp+168h+ppv], rax; int
0x18003bd44  mov     r9, r12
0x18003bd47  xor     r8d, r8d
0x18003bd4a  xor     edx, edx
0x18003bd4c  mov     rcx, rbx
0x18003bd4f  mov     rax, r14
0x18003bd52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd57  mov     rcx, [rsp+168h]; this
0x18003bd5f  xor     ebx, ebx
0x18003bd61  test    eax, eax
0x18003bd63  jns     short loc_18003BD7A
0x18003bd65  mov     r9d, eax; char *
0x18003bd68  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18003bd6f  mov     edx, 57Fh; void *
0x18003bd74  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003bd7a  lea     rcx, [rsp+168h+var_120]
0x18003bd7f  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18003bd84  nop
0x18003bd85  lea     rcx, [rsp+168h+var_110]
0x18003bd8a  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18003bd8f  nop
0x18003bd90  lea     rcx, [rsp+168h+var_118]
0x18003bd95  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18003bd9a  mov     rcx, [rsp+168h+var_100]
0x18003bd9f  lea     r14, [r15+30h]
0x18003bda3  mov     [rsp+168h+var_C8], rbx
0x18003bdab  lea     r9, [rsp+168h+var_C8]
0x18003bdb3  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x18003bdba  xor     edx, edx
0x18003bdbc  call    cs:__imp_CreateRandomAccessStreamOverStream
0x18003bdc3  nop     dword ptr [rax+rax+00h]
0x18003bdc8  mov     rcx, [rsp+168h]; this
0x18003bdd0  test    eax, eax
0x18003bdd2  jns     short loc_18003BDE8
0x18003bdd4  mov     r9d, eax; char *
0x18003bdd7  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18003bdde  mov     edx, 584h; void *
0x18003bde3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003bde8  lea     rcx, [rsp+168h+var_B0]
0x18003bdf0  call    ??$GetActivationFactory@UIRandomAccessStreamReferenceStatics@Streams@Storage@Windows@@@wil@@YA?AV?$com_ptr_t@UIRandomAccessStreamReferenceStatics@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Storage::Streams::IRandomAccessStreamReferenceStatics>(ushort const *)
0x18003bdf5  nop
0x18003bdf6  mov     [rsp+168h+var_E8], rbx
0x18003bdfe  mov     rcx, [rsp+168h+var_B0]
0x18003be06  mov     rax, [rcx]
0x18003be09  mov     [rsp+168h+var_E8], rbx
0x18003be11  lea     r8, [rsp+168h+var_E8]
0x18003be19  mov     rdx, [rsp+168h+var_C8]
0x18003be21  mov     rax, [rax+40h]
0x18003be25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be2a  mov     rcx, [rsp+168h]; this
0x18003be32  test    eax, eax
0x18003be34  jns     short loc_18003BE4A
0x18003be36  mov     r9d, eax; char *
0x18003be39  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18003be40  mov     edx, 587h; void *
0x18003be45  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003be4a  mov     eax, [r15+20h]
0x18003be4e  mov     [rsp+168h+var_110], eax
0x18003be52  lea     rcx, [rsp+168h+var_B8]
0x18003be5a  call    ??$GetActivationFactory@UIUserManagerStatics6@Internal@System@Windows@@@wil@@YA?AV?$com_ptr_t@UIUserManagerStatics6@Internal@System@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::System::Internal::IUserManagerStatics6>(ushort const *)
0x18003be5f  nop
0x18003be60  mov     rbx, [rdi]
0x18003be63  xor     r15d, r15d
0x18003be66  mov     [rsp+168h+var_50], r15
0x18003be6e  mov     [rsp+168h+var_120], r15d
0x18003be73  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003be77  inc     rcx; unsigned __int64
0x18003be7a  cmp     [rbx+rcx*2], r15w
0x18003be7f  jnz     short loc_18003BE77
0x18003be81  lea     rdx, [rsp+168h+var_120]; unsigned int *
0x18003be86  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18003be8b  test    eax, eax
0x18003be8d  jns     short loc_18003BE97
0x18003be8f  mov     ecx, eax; this
0x18003be91  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003be96  int     3; Trap to Debugger
0x18003be97  mov     ecx, [rsp+168h+var_120]; unsigned int
0x18003be9b  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18003bea0  mov     r9d, [rsp+168h+var_120]; unsigned int
0x18003bea5  mov     r8d, eax; unsigned int
0x18003bea8  mov     rdx, rbx; sourceString
0x18003beab  lea     rcx, [rsp+168h+hstringHeader]; hstringHeader
0x18003beb3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003beb8  nop
0x18003beb9  mov     rax, [rsp+168h+var_50]
0x18003bec1  mov     qword ptr [rsp+168h+var_120], rax
0x18003bec6  mov     rax, [rsp+168h+var_E8]
0x18003bece  mov     qword ptr [rsp+168h+var_A0], rax
0x18003bed6  mov     rax, [rsp+168h+var_E0]
0x18003bede  mov     [rsp+168h+var_C0], rax
0x18003bee6  lea     rax, [rsp+168h+var_120]
0x18003beeb  mov     [rsp+168h+var_138], rax
0x18003bef0  lea     rax, [rsp+168h+var_110]
0x18003bef5  mov     [rsp+168h+var_140], rax
0x18003befa  lea     rax, [rsp+168h+var_A0]
0x18003bf02  mov     [rsp+168h+ppv], rax; int
0x18003bf07  lea     r9, [rsp+168h+var_C0]
0x18003bf0f  mov     rdx, [rsp+168h+var_B8]
0x18003bf17  lea     rcx, [rsp+168h+var_118]
0x18003bf1c  call    ??$call_and_wait_for_completion@UIUserManagerStatics6@Internal@System@Windows@@PEAUIUser@34@PEAUIRandomAccessStreamReference@Streams@Storage@4@IPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@4@$$ZPEAU534@PEAU6784@AEAIPEAU9@@wil@@YA?A_PPEAUIUserManagerStatics6@Internal@System@Windows@@P81234@EAAJPEAUIUser@34@PEAUIRandomAccessStreamReference@Streams@Storage@4@IPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@4@@Z$$QEAPEAU534@$$QEAPEAU6784@AEAI$$QEAPEAU9@@Z
0x18003bf21  mov     rbx, [rax]
0x18003bf24  mov     [rax], r15
0x18003bf27  mov     [rsp+168h+var_C0], rbx
0x18003bf2f  mov     rcx, [rsp+168h+var_118]
  ... truncated ...
```
