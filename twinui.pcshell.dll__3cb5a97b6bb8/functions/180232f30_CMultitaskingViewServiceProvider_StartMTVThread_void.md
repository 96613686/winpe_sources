# CMultitaskingViewServiceProvider::_StartMTVThread(void)

- ea: `0x180232f30`
- end: `0x180233b9d`
- name: `?_StartMTVThread@CMultitaskingViewServiceProvider@@AEAAJXZ`
- size: `3181`
- prototype: `__int64 __fastcall(CMultitaskingViewServiceProvider *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1804ddcc0`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x180031c70`
- `0x1800358f0`
- `0x18004ec18`
- `0x18011ebe4`
- `0x18014b090`
- `0x180180a9c`
- `0x1801de050`
- `0x180232f30`
- `0x1802bbaf8`
- `0x1802dc824`
- `0x180356384`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180233a34`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180233a34`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1802330db`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180233152`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1802331c8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18023320c`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180233286`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1802332f9`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18023336a`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1802334ce`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1802335c9`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180233642`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1802336b8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180233735`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1802337c3`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180233803`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18023388e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180233901`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180233971`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1802339da`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1802330db`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180233152`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1802331c8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18023320c`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180233286`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1802332f9`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18023336a`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1802334ce`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1802335c9`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180233642`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1802336b8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180233735`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1802337c3`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180233803`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18023388e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180233901`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180233971`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1802339da`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180233a94`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180233a94`

## string_xrefs

- `0x18023300b`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x18023306c`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x1802330ec`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x180233163`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x18023323a`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x180233297`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x180233327`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x18023337b`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x180233413`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x180233468`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x1802334df`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x180233560`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x1802335da`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x180233653`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x1802336c9`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x180233746`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x180233831`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x1802338bf`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x180233912`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x1802339a2`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x180233a15`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`
- `0x180233a52`: `pcshell\twinui\multitaskingview\lib\multitaskingviewserviceprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall CMultitaskingViewServiceProvider::_StartMTVThread(CMultitaskingViewServiceProvider *this)
{
  _QWORD *v2; // rsi
  unsigned int LastError; // ebx
  int v4; // eax
  __int64 v5; // rdx
  HRESULT v6; // eax
  __int64 v7; // rdx
  HRESULT v8; // eax
  __int64 v9; // rdx
  int v10; // eax
  HRESULT v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  HRESULT v14; // eax
  __int64 v15; // rdx
  void (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // rdi
  void (__fastcall *v17)(_QWORD, GUID *, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64 *); // rbx
  int v21; // eax
  __int64 v22; // rdx
  HRESULT v23; // eax
  __int64 v24; // rdx
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v26)(_QWORD, GUID *, __int64 *); // rbx
  int v27; // eax
  __int64 v28; // rdx
  HRESULT v29; // eax
  __int64 v30; // rdx
  HRESULT v31; // eax
  __int64 v32; // rdx
  HRESULT v33; // eax
  __int64 v34; // rdx
  HRESULT v35; // eax
  __int64 v36; // rdx
  __int64 v37; // rdx
  int v38; // eax
  int v39; // eax
  HRESULT v40; // eax
  __int64 v41; // rdx
  int v42; // eax
  HRESULT v43; // eax
  wil::details::in1diag3 *v44; // rcx
  __int64 v45; // rdx
  HANDLE EventW; // rdi
  const char *v47; // r9
  __int64 v48; // rdx
  unsigned int v49; // edx
  int v51[2]; // [rsp+20h] [rbp-89h] BYREF
  void *ppvOut; // [rsp+28h] [rbp-81h] BYREF
  void *v53; // [rsp+30h] [rbp-79h] BYREF
  void *v54; // [rsp+38h] [rbp-71h] BYREF
  void *v55; // [rsp+40h] [rbp-69h] BYREF
  void *v56; // [rsp+48h] [rbp-61h] BYREF
  void *v57; // [rsp+50h] [rbp-59h] BYREF
  void *v58; // [rsp+58h] [rbp-51h] BYREF
  __int64 v59; // [rsp+60h] [rbp-49h] BYREF
  __int64 v60; // [rsp+68h] [rbp-41h] BYREF
  void *v61; // [rsp+70h] [rbp-39h] BYREF
  __int64 v62; // [rsp+78h] [rbp-31h] BYREF
  void *v63; // [rsp+80h] [rbp-29h] BYREF
  void *v64; // [rsp+88h] [rbp-21h] BYREF
  void *v65; // [rsp+90h] [rbp-19h] BYREF
  void *v66; // [rsp+98h] [rbp-11h] BYREF
  void *v67; // [rsp+A0h] [rbp-9h] BYREF
  void *v68; // [rsp+A8h] [rbp-1h] BYREF
  void *v69; // [rsp+B0h] [rbp+7h] BYREF
  void *v70; // [rsp+B8h] [rbp+Fh] BYREF
  void *v71; // [rsp+C0h] [rbp+17h] BYREF
  void *v72; // [rsp+C8h] [rbp+1Fh] BYREF
  _QWORD *v73; // [rsp+D0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v2 = operator new(0xC8u, (const struct std::nothrow_t *)std::nothrow);
  if ( v2 )
  {
    v2[24] = 0;
    *v2 = 0;
    v2[1] = 0;
    v2[2] = 0;
    v2[3] = 0;
    v2[4] = 0;
    v2[5] = 0;
    v2[6] = 0;
    v2[7] = 0;
    v2[8] = 0;
    v2[9] = 0;
    v2[10] = 0;
    v2[11] = 0;
    v2[12] = 0;
    v2[13] = 0;
    v2[14] = 0;
    v2[15] = 0;
    v2[16] = 0;
    v2[17] = 0;
    v2[18] = 0;
    v2[19] = 0;
    v2[20] = 0;
    v2[21] = 0;
    v2[22] = 0;
    v2[23] = 0;
  }
  else
  {
    v2 = 0;
  }
  v73 = v2;
  if ( v2 )
  {
    *(_QWORD *)v51 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v51);
    Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CImmersiveShellComponentWithSite,IMultitaskingViewServiceProvider,IMultitaskingViewTaskScheduler>>(
      this,
      &GUID_90adbab9_cdb8_43dd_8daa_ba1180be5215,
      v51);
    v4 = CMarshaledInterface::Marshal(v2, &GUID_90adbab9_cdb8_43dd_8daa_ba1180be5215, *(_QWORD *)v51, 2);
    LastError = v4;
    if ( v4 < 0 )
    {
      v5 = 304;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
        (const char *)(unsigned int)v4,
        v51[0]);
LABEL_9:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v51);
      goto LABEL_121;
    }
    v4 = CMarshaledInterface::Marshal(v2 + 1, &GUID_1841c6d7_4f9d_42c0_af41_8747538f10e5, *((_QWORD *)this + 28), 2);
    LastError = v4;
    if ( v4 < 0 )
    {
      v5 = 306;
      goto LABEL_8;
    }
    ppvOut = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
    v6 = IUnknown_QueryService(
           *((IUnknown **)this + 2),
           &GUID_e0fe7384_5482_4659_ab2c_4ff038948779,
           &GUID_e0fe7384_5482_4659_ab2c_4ff038948779,
           &ppvOut);
    LastError = v6;
    if ( v6 < 0 )
    {
      v7 = 309;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
        (const char *)(unsigned int)v6,
        v51[0]);
LABEL_15:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
      goto LABEL_9;
    }
    v6 = CMarshaledInterface::Marshal(v2 + 3, &GUID_e0fe7384_5482_4659_ab2c_4ff038948779, ppvOut, 2);
    LastError = v6;
    if ( v6 < 0 )
    {
      v7 = 310;
      goto LABEL_14;
    }
    v53 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    v8 = IUnknown_QueryService(
           *((IUnknown **)this + 2),
           &GUID_af6eec2f_c097_4f4a_b536_3cb918550cb3,
           &GUID_af6eec2f_c097_4f4a_b536_3cb918550cb3,
           &v53);
    LastError = v8;
    if ( v8 < 0 )
    {
      v9 = 313;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
        (const char *)(unsigned int)v8,
        v51[0]);
LABEL_21:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
      goto LABEL_15;
    }
    v8 = CMarshaledInterface::Marshal(v2 + 2, &GUID_af6eec2f_c097_4f4a_b536_3cb918550cb3, v53, 2);
    LastError = v8;
    if ( v8 < 0 )
    {
      v9 = 314;
      goto LABEL_20;
    }
    v55 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
    if ( IUnknown_QueryService(
           *((IUnknown **)this + 2),
           (const GUID *const)&SID_VirtualDesktopManager,
           &GUID_4970ba3d_fd4e_4647_bea3_d89076ef4b9c,
           &v55) >= 0 )
      CMarshaledInterface::Marshal(v2 + 4, &GUID_4970ba3d_fd4e_4647_bea3_d89076ef4b9c, v55, 2);
    v54 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
    if ( IUnknown_QueryService(
           *((IUnknown **)this + 2),
           (const GUID *const)&SID_VirtualDesktopPinnedApps,
           &GUID_4ce81583_1e4c_4632_a621_07a53543148f,
           &v54) >= 0 )
    {
      v10 = CMarshaledInterface::Marshal(v2 + 5, &GUID_4ce81583_1e4c_4632_a621_07a53543148f, v54, 2);
      LastError = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x145,
          (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
          (const char *)(unsigned int)v10,
          v51[0]);
LABEL_29:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
        goto LABEL_21;
      }
    }
    v56 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
    v11 = IUnknown_QueryService(
            *((IUnknown **)this + 2),
            &GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a,
            &GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a,
            &v56);
    LastError = v11;
    if ( v11 < 0 )
    {
      v12 = 329;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
        (const char *)(unsigned int)v11,
        v51[0]);
LABEL_33:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
      goto LABEL_29;
    }
    v11 = CMarshaledInterface::Marshal(v2 + 6, &GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a, v56, 2);
    LastError = v11;
    if ( v11 < 0 )
    {
      v12 = 330;
      goto LABEL_32;
    }
    v57 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
    if ( IUnknown_QueryService(
           *((IUnknown **)this + 2),
           (const GUID *const)&SID_VirtualDesktopNotificationService,
           &GUID_0cd45e71_d927_4f15_8b0a_8fef525337bf,
           &v57) >= 0 )
    {
      v13 = CMarshaledInterface::Marshal(v2 + 7, &GUID_0cd45e71_d927_4f15_8b0a_8fef525337bf, v57, 2);
      LastError = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14F,
          (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
          (const char *)(unsigned int)v13,
          v51[0]);
LABEL_39:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
        goto LABEL_33;
      }
    }
    v58 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
    v14 = IUnknown_QueryService(
            *((IUnknown **)this + 2),
            &stru_1807A44E8,
            &GUID_103231ae_04cb_4e5e_b63d_e3ce47cd0f0a,
            &v58);
    LastError = v14;
    if ( v14 < 0 )
    {
      v15 = 339;
LABEL_42:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
        (const char *)(unsigned int)v14,
        v51[0]);
LABEL_43:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
      goto LABEL_39;
    }
    v14 = CMarshaledInterface::Marshal(v2 + 8, &GUID_103231ae_04cb_4e5e_b63d_e3ce47cd0f0a, v58, 2);
    LastError = v14;
    if ( v14 < 0 )
    {
      v15 = 340;
      goto LABEL_42;
    }
    v59 = 0;
    v16 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 25);
    v17 = **v16;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
    v17(v16, &GUID_6e7da126_f47e_4b81_b43f_e466cf325f58, &v59);
    v18 = CMarshaledInterface::Marshal(v2 + 9, &GUID_6e7da126_f47e_4b81_b43f_e466cf325f58, v59, 2);
    LastError = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x158,
        (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
        (const char *)(unsigned int)v18,
        v51[0]);
LABEL_48:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
      goto LABEL_43;
    }
    v60 = 0;
    v19 = *((_QWORD *)this + 22);
    v20 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    v21 = v20(v19, &v60);
    LastError = v21;
    if ( v21 < 0 )
    {
      v22 = 347;
LABEL_51:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
        (const char *)(unsigned int)v21,
        v51[0]);
LABEL_52:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
      goto LABEL_48;
    }
    v21 = CMarshaledInterface::Marshal(v2 + 10, &GUID_4639c886_cffe_492c_915a_1e3f02d22434, v60, 2);
    LastError = v21;
    if ( v21 < 0 )
    {
      v22 = 348;
      goto LABEL_51;
    }
    v61 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    v23 = IUnknown_QueryService(
            *((IUnknown **)this + 2),
            &stru_1807A44D8,
            &GUID_4214f6fa_eb36_4e2f_9ca2_23fdc1832df7,
            &v61);
    LastError = v23;
    if ( v23 < 0 )
    {
      v24 = 351;
LABEL_57:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
        (const char *)(unsigned int)v23,
        v51[0]);
LABEL_58:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
      goto LABEL_52;
    }
    v23 = CMarshaledInterface::Marshal(v2 + 11, &GUID_4214f6fa_eb36_4e2f_9ca2_23fdc1832df7, v61, 2);
    LastError = v23;
    if ( v23 < 0 )
    {
      v24 = 352;
      goto LABEL_57;
    }
    v62 = 0;
    v25 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 26);
    v26 = **v25;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    v27 = v26(v25, &GUID_373e56cf_0a1b_4b4a_a1a4_a46b25ffd7e3, &v62);
    LastError = v27;
    if ( v27 < 0 )
    {
      v28 = 355;
LABEL_63:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
        (const char *)(unsigned int)v27,
        v51[0]);
LABEL_64:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
      goto LABEL_58;
    }
    v27 = CMarshaledInterface::Marshal(v2 + 12, &GUID_373e56cf_0a1b_4b4a_a1a4_a46b25ffd7e3, v62, 2);
    LastError = v27;
    if ( v27 < 0 )
    {
      v28 = 356;
      goto LABEL_63;
    }
    v63 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    v29 = IUnknown_QueryService(
            *((IUnknown **)this + 2),
            (const GUID *const)&SID_ShellTargetingTracker,
            &GUID_c59a546b_412b_40f3_b151_9b3202e2835f,
            &v63);
    LastError = v29;
    if ( v29 < 0 )
    {
      v30 = 359;
LABEL_69:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
        (const char *)(unsigned int)v29,
        v51[0]);
LABEL_70:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
      goto LABEL_64;
    }
    v29 = CMarshaledInterface::Marshal(v2 + 13, &GUID_c59a546b_412b_40f3_b151_9b3202e2835f, v63, 2);
    LastError = v29;
    if ( v29 < 0 )
    {
      v30 = 360;
      goto LABEL_69;
    }
    v64 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
    v31 = IUnknown_QueryService(
            *((IUnknown **)this + 2),
            &GUID_fff59320_db70_4865_8fed_8b502d692f12,
            &GUID_fff59320_db70_4865_8fed_8b502d692f12,
            &v64);
    LastError = v31;
    if ( v31 < 0 )
    {
      v32 = 363;
LABEL_75:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
        (const char *)(unsigned int)v31,
        v51[0]);
LABEL_76:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
      goto LABEL_70;
    }
    v31 = CMarshaledInterface::Marshal(v2 + 14, &GUID_fff59320_db70_4865_8fed_8b502d692f12, v64, 2);
    LastError = v31;
    if ( v31 < 0 )
    {
      v32 = 364;
      goto LABEL_75;
    }
    v65 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    v33 = IUnknown_QueryService(
            *((IUnknown **)this + 2),
            (const GUID *const)&SID_ApplicationViewIconLoaderService,
            &GUID_f622d8ac_35d3_4374_9148_66f1f7894191,
            &v65);
    LastError = v33;
    if ( v33 < 0 )
    {
      v34 = 376;
LABEL_81:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
        (const char *)(unsigned int)v33,
        v51[0]);
LABEL_82:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
      goto LABEL_76;
    }
    v33 = CMarshaledInterface::Marshal(v2 + 16, &GUID_f622d8ac_35d3_4374_9148_66f1f7894191, v65, 2);
    LastError = v33;
    if ( v33 < 0 )
    {
      v34 = 377;
      goto LABEL_81;
    }
    v66 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    v35 = IUnknown_QueryService(
            *((IUnknown **)this + 2),
            (const GUID *const)&SID_IImmersiveMonitorService,
            &GUID_4d4c1e64_e410_4faa_bafa_59ca069bfec2,
            &v66);
    LastError = v35;
    if ( v35 < 0 )
    {
      v36 = 380;
LABEL_87:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
        (const char *)(unsigned int)v35,
        v51[0]);
LABEL_88:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
      goto LABEL_82;
    }
    v35 = CMarshaledInterface::Marshal(v2 + 19, &GUID_4d4c1e64_e410_4faa_bafa_59ca069bfec2, v66, 2);
    LastError = v35;
    if ( v35 < 0 )
    {
      v36 = 381;
      goto LABEL_87;
    }
    LOBYTE(v37) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_XamlAllUpView>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_XamlAllUpView>::GetImpl'::`2'::impl,
      v37);
    v71 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
    IUnknown_QueryService(
      *((IUnknown **)this + 2),
      (const GUID *const)&SID_VirtualDesktopDataSource,
      &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
      &v71);
    if ( v71 )
      CMarshaledInterface::Marshal(v2 + 17, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, v71, 2);
    v70 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
    IUnknown_QueryService(
      *((IUnknown **)this + 2),
      (const GUID *const)&SID_VirtualDesktopController,
      &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
      &v70);
    if ( v70 )
    {
      v38 = CMarshaledInterface::Marshal(v2 + 18, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, v70, 2);
      LastError = v38;
      if ( v38 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18D,
          (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
          (const char *)(unsigned int)v38,
          v51[0]);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
        goto LABEL_88;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
    v67 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
    if ( IUnknown_QueryService(
           *((IUnknown **)this + 2),
           &stru_1807A4508,
           &GUID_8bc0416b_e6fa_4b43_9553_9386b4584de0,
           &v67) >= 0 )
    {
      v39 = CMarshaledInterface::Marshal(v2 + 20, &GUID_8bc0416b_e6fa_4b43_9553_9386b4584de0, v67, 2);
      LastError = v39;
      if ( v39 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x194,
          (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
          (const char *)(unsigned int)v39,
          v51[0]);
LABEL_99:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
        goto LABEL_88;
      }
    }
    v68 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    v40 = IUnknown_QueryService(
            *((IUnknown **)this + 2),
            (const GUID *const)&SID_ImmersiveShellHookService,
            &GUID_914d9b3a_5e53_4e14_bbba_46062acb35a4,
            &v68);
    LastError = v40;
    if ( v40 < 0 )
    {
      v41 = 408;
LABEL_102:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v41,
        (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
        (const char *)(unsigned int)v40,
        v51[0]);
LABEL_103:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
      goto LABEL_99;
    }
    v40 = CMarshaledInterface::Marshal(v2 + 21, &GUID_914d9b3a_5e53_4e14_bbba_46062acb35a4, v68, 2);
    LastError = v40;
    if ( v40 < 0 )
    {
      v41 = 409;
      goto LABEL_102;
    }
    v69 = 0;
    if ( IUnknown_QueryService(
           *((IUnknown **)this + 2),
           &winrt::impl::guid_v<winrt::Windows::Internal::UI::Shell::IWindowTabExtension>,
           &GUID_0e84cceb_709b_52d2_a663_ec5130862a9b,
           &v69) >= 0 )
    {
      v42 = CMarshaledInterface::Marshal(v2 + 22, &GUID_0e84cceb_709b_52d2_a663_ec5130862a9b, v69, 2);
      LastError = v42;
      if ( v42 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x19F,
          (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
          (const char *)(unsigned int)v42,
          v51[0]);
LABEL_109:
        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v69);
        goto LABEL_103;
      }
    }
    v72 = 0;
    v43 = IUnknown_QueryService(
            *((IUnknown **)this + 2),
            &GUID_cb6e4ee4_9424_5bb0_b290_0e37b7c5c386,
            &GUID_cb6e4ee4_9424_5bb0_b290_0e37b7c5c386,
            &v72);
    v44 = retaddr;
    if ( v43 >= 0 )
    {
      v43 = CMarshaledInterface::Marshal(v2 + 23, &GUID_cb6e4ee4_9424_5bb0_b290_0e37b7c5c386, v72, 2);
      v44 = retaddr;
      if ( v43 >= 0 )
      {
LABEL_115:
        EventW = CreateEventW(0, 1, 0, 0);
        CAutoHandle<void *>::~CAutoHandle<void *>((char *)this + 240);
        *((_QWORD *)this + 30) = EventW;
        if ( EventW )
        {
          v2[24] = EventW;
          v73 = 0;
          if ( SHCreateThread(
                 CMultitaskingViewServiceProvider::s_RunMTVThread,
                 v2,
                 8u,
                 CMultitaskingViewServiceProvider::s_InitMTVThread) )
          {
            wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v72);
            wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v69);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v51);
            LastError = 0;
            goto LABEL_121;
          }
          CMultitaskingViewServiceProvider::INIT_THREAD_DATA::`scalar deleting destructor'(
            (CMultitaskingViewServiceProvider::INIT_THREAD_DATA *)v2,
            v49);
          v48 = 436;
        }
        else
        {
          v48 = 427;
        }
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v48,
                      (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
                      v47);
        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v72);
        goto LABEL_109;
      }
      v45 = 421;
    }
    else
    {
      v45 = 419;
    }
    wil::details::in1diag3::_Log_Hr(
      v44,
      (void *)v45,
      (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
      (const char *)(unsigned int)v43,
      v51[0]);
    goto LABEL_115;
  }
  LastError = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x12B,
    (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\multitaskingviewserviceprovider.cpp",
    (const char *)0x8007000ELL,
    v51[0]);
LABEL_121:
  CAutoMemPtr<CMultitaskingViewServiceProvider::INIT_THREAD_DATA>::~CAutoMemPtr<CMultitaskingViewServiceProvider::INIT_THREAD_DATA>(&v73);
  return LastError;
}

```

## disassembly

```asm
0x180232f30  mov     [rsp-8+arg_8], rbx
0x180232f35  mov     [rsp-8+arg_10], rsi
0x180232f3a  push    rbp
0x180232f3b  push    rdi
0x180232f3c  push    r12
0x180232f3e  push    r14
0x180232f40  push    r15
0x180232f42  lea     rbp, [rsp-37h]
0x180232f47  sub     rsp, 0E0h
0x180232f4e  mov     r14, rcx
0x180232f51  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180232f58  mov     ecx, 0C8h; unsigned __int64
0x180232f5d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180232f62  mov     rsi, rax
0x180232f65  xor     r15d, r15d
0x180232f68  test    rax, rax
0x180232f6b  jz      loc_180232FF3
0x180232f71  xor     eax, eax
0x180232f73  mov     [rsi+0C0h], rax
0x180232f7a  mov     [rsi], r15
0x180232f7d  mov     [rsi+8], r15
0x180232f81  mov     [rsi+10h], r15
0x180232f85  mov     [rsi+18h], r15
0x180232f89  mov     [rsi+20h], r15
0x180232f8d  mov     [rsi+28h], r15
0x180232f91  mov     [rsi+30h], r15
0x180232f95  mov     [rsi+38h], r15
0x180232f99  mov     [rsi+40h], r15
0x180232f9d  mov     [rsi+48h], r15
0x180232fa1  mov     [rsi+50h], r15
0x180232fa5  mov     [rsi+58h], r15
0x180232fa9  mov     [rsi+60h], r15
0x180232fad  mov     [rsi+68h], r15
0x180232fb1  mov     [rsi+70h], r15
0x180232fb5  mov     [rsi+78h], r15
0x180232fb9  mov     [rsi+80h], r15
0x180232fc0  mov     [rsi+88h], r15
0x180232fc7  mov     [rsi+90h], r15
0x180232fce  mov     [rsi+98h], r15
0x180232fd5  mov     [rsi+0A0h], r15
0x180232fdc  mov     [rsi+0A8h], r15
0x180232fe3  mov     [rsi+0B0h], r15
0x180232fea  mov     [rsi+0B8h], r15
0x180232ff1  jmp     short loc_180232FF6
0x180232ff3  mov     rsi, r15
0x180232ff6  mov     [rbp+57h+var_30], rsi
0x180232ffa  test    rsi, rsi
0x180232ffd  jnz     short loc_180233021
0x180232fff  mov     rcx, [rbp+5Fh]; this
0x180233003  mov     ebx, 8007000Eh
0x180233008  mov     r9d, ebx; char *
0x18023300b  lea     r8, aPcshellTwinuiM_50; "pcshell\\twinui\\multitaskingview\\lib"...
0x180233012  mov     edx, 12Bh; void *
0x180233017  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18023301c  jmp     loc_180233B76
0x180233021  mov     qword ptr [rsp+100h+var_E0], r15; int
0x180233026  lea     rcx, [rsp+100h+var_E0]
0x18023302b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180233030  lea     r8, [rsp+100h+var_E0]
0x180233035  lea     rdx, _GUID_90adbab9_cdb8_43dd_8daa_ba1180be5215
0x18023303c  mov     rcx, r14
0x18023303f  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCImmersiveShellComponentWithSite@@UIMultitaskingViewServiceProvider@@UIMultitaskingViewTaskScheduler@@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCImmersiveShellComponentWithSite@@UIMultitaskingViewServiceProvider@@UIMultitaskingViewTaskScheduler@@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CImmersiveShellComponentWithSite,IMultitaskingViewServiceProvider,IMultitaskingViewTaskScheduler>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CImmersiveShellComponentWithSite,IMultitaskingViewServiceProvider,IMultitaskingViewTaskScheduler> *,_GUID const &,void * *)
0x180233044  mov     r12d, 2
0x18023304a  mov     r9d, r12d
0x18023304d  mov     r8, qword ptr [rsp+100h+var_E0]
0x180233052  lea     rdx, _GUID_90adbab9_cdb8_43dd_8daa_ba1180be5215
0x180233059  mov     rcx, rsi
0x18023305c  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x180233061  mov     ebx, eax
0x180233063  test    eax, eax
0x180233065  jns     short loc_18023308F
0x180233067  mov     edx, 130h; void *
0x18023306c  lea     r8, aPcshellTwinuiM_50; "pcshell\\twinui\\multitaskingview\\lib"...
0x180233073  mov     r9d, eax; char *
0x180233076  mov     rcx, [rbp+5Fh]; this
0x18023307a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18023307f  nop
0x180233080  lea     rcx, [rsp+100h+var_E0]
0x180233085  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18023308a  jmp     loc_180233B76
0x18023308f  lea     rcx, [rsi+8]
0x180233093  mov     r9d, r12d
0x180233096  mov     r8, [r14+0E0h]
0x18023309d  lea     rdx, _GUID_1841c6d7_4f9d_42c0_af41_8747538f10e5
0x1802330a4  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x1802330a9  mov     ebx, eax
0x1802330ab  test    eax, eax
0x1802330ad  jns     short loc_1802330B6
0x1802330af  mov     edx, 132h
0x1802330b4  jmp     short loc_18023306C
0x1802330b6  mov     [rsp+100h+ppvOut], r15
0x1802330bb  lea     rcx, [rsp+100h+ppvOut]
0x1802330c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802330c5  lea     r9, [rsp+100h+ppvOut]; ppvOut
0x1802330ca  lea     rdi, _GUID_e0fe7384_5482_4659_ab2c_4ff038948779
0x1802330d1  mov     r8, rdi; riid
0x1802330d4  mov     rdx, rdi; guidService
0x1802330d7  mov     rcx, [r14+10h]; punk
0x1802330db  call    cs:__imp_IUnknown_QueryService
0x1802330e1  mov     ebx, eax
0x1802330e3  test    eax, eax
0x1802330e5  jns     short loc_18023310F
0x1802330e7  mov     edx, 135h; void *
0x1802330ec  lea     r8, aPcshellTwinuiM_50; "pcshell\\twinui\\multitaskingview\\lib"...
0x1802330f3  mov     r9d, eax; char *
0x1802330f6  mov     rcx, [rbp+5Fh]; this
0x1802330fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802330ff  nop
0x180233100  lea     rcx, [rsp+100h+ppvOut]
0x180233105  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18023310a  jmp     loc_180233080
0x18023310f  lea     rcx, [rsi+18h]
0x180233113  mov     r9d, r12d
0x180233116  mov     r8, [rsp+100h+ppvOut]
0x18023311b  mov     rdx, rdi
0x18023311e  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x180233123  mov     ebx, eax
0x180233125  test    eax, eax
0x180233127  jns     short loc_180233130
0x180233129  mov     edx, 136h
0x18023312e  jmp     short loc_1802330EC
0x180233130  mov     [rbp+57h+var_D0], r15
0x180233134  lea     rcx, [rbp+57h+var_D0]
0x180233138  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18023313d  lea     r9, [rbp+57h+var_D0]; ppvOut
0x180233141  lea     rdi, _GUID_af6eec2f_c097_4f4a_b536_3cb918550cb3
0x180233148  mov     r8, rdi; riid
0x18023314b  mov     rdx, rdi; guidService
0x18023314e  mov     rcx, [r14+10h]; punk
0x180233152  call    cs:__imp_IUnknown_QueryService
0x180233158  mov     ebx, eax
0x18023315a  test    eax, eax
0x18023315c  jns     short loc_180233185
0x18023315e  mov     edx, 139h; void *
0x180233163  lea     r8, aPcshellTwinuiM_50; "pcshell\\twinui\\multitaskingview\\lib"...
0x18023316a  mov     r9d, eax; char *
0x18023316d  mov     rcx, [rbp+5Fh]; this
0x180233171  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180233176  nop
0x180233177  lea     rcx, [rbp+57h+var_D0]
0x18023317b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180233180  jmp     loc_180233100
0x180233185  lea     rcx, [rsi+10h]
0x180233189  mov     r9d, r12d
0x18023318c  mov     r8, [rbp+57h+var_D0]
0x180233190  mov     rdx, rdi
0x180233193  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x180233198  mov     ebx, eax
0x18023319a  test    eax, eax
0x18023319c  jns     short loc_1802331A5
0x18023319e  mov     edx, 13Ah
0x1802331a3  jmp     short loc_180233163
0x1802331a5  mov     [rbp+57h+var_C0], r15
0x1802331a9  lea     rcx, [rbp+57h+var_C0]
0x1802331ad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802331b2  lea     r9, [rbp+57h+var_C0]; ppvOut
0x1802331b6  lea     r8, _GUID_4970ba3d_fd4e_4647_bea3_d89076ef4b9c; riid
0x1802331bd  lea     rdx, SID_VirtualDesktopManager; guidService
0x1802331c4  mov     rcx, [r14+10h]; punk
0x1802331c8  call    cs:__imp_IUnknown_QueryService
0x1802331ce  test    eax, eax
0x1802331d0  js      short loc_1802331E9
0x1802331d2  lea     rcx, [rsi+20h]
0x1802331d6  mov     r9d, r12d
0x1802331d9  mov     r8, [rbp+57h+var_C0]
0x1802331dd  lea     rdx, _GUID_4970ba3d_fd4e_4647_bea3_d89076ef4b9c
0x1802331e4  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x1802331e9  mov     [rbp+57h+var_C8], r15
0x1802331ed  lea     rcx, [rbp+57h+var_C8]
0x1802331f1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802331f6  lea     r9, [rbp+57h+var_C8]; ppvOut
0x1802331fa  lea     r8, _GUID_4ce81583_1e4c_4632_a621_07a53543148f; riid
0x180233201  lea     rdx, SID_VirtualDesktopPinnedApps; guidService
0x180233208  mov     rcx, [r14+10h]; punk
0x18023320c  call    cs:__imp_IUnknown_QueryService
0x180233212  test    eax, eax
0x180233214  js      short loc_180233264
0x180233216  lea     rcx, [rsi+28h]
0x18023321a  mov     r9d, r12d
0x18023321d  mov     r8, [rbp+57h+var_C8]
0x180233221  lea     rdx, _GUID_4ce81583_1e4c_4632_a621_07a53543148f
0x180233228  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x18023322d  mov     ebx, eax
0x18023322f  test    eax, eax
0x180233231  jns     short loc_180233264
0x180233233  mov     rcx, [rbp+5Fh]; this
0x180233237  mov     r9d, eax; char *
0x18023323a  lea     r8, aPcshellTwinuiM_50; "pcshell\\twinui\\multitaskingview\\lib"...
0x180233241  mov     edx, 145h; void *
0x180233246  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18023324b  nop
0x18023324c  lea     rcx, [rbp+57h+var_C8]
0x180233250  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180233255  nop
0x180233256  lea     rcx, [rbp+57h+var_C0]
0x18023325a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18023325f  jmp     loc_180233177
0x180233264  mov     [rbp+57h+var_B8], r15
0x180233268  lea     rcx, [rbp+57h+var_B8]
0x18023326c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180233271  lea     r9, [rbp+57h+var_B8]; ppvOut
0x180233275  lea     rdi, _GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a
0x18023327c  mov     r8, rdi; riid
0x18023327f  mov     rdx, rdi; guidService
0x180233282  mov     rcx, [r14+10h]; punk
0x180233286  call    cs:__imp_IUnknown_QueryService
0x18023328c  mov     ebx, eax
0x18023328e  test    eax, eax
0x180233290  jns     short loc_1802332B6
0x180233292  mov     edx, 149h; void *
0x180233297  lea     r8, aPcshellTwinuiM_50; "pcshell\\twinui\\multitaskingview\\lib"...
0x18023329e  mov     r9d, eax; char *
0x1802332a1  mov     rcx, [rbp+5Fh]; this
0x1802332a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802332aa  nop
0x1802332ab  lea     rcx, [rbp+57h+var_B8]
0x1802332af  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802332b4  jmp     short loc_18023324C
0x1802332b6  lea     rcx, [rsi+30h]
0x1802332ba  mov     r9d, r12d
0x1802332bd  mov     r8, [rbp+57h+var_B8]
0x1802332c1  mov     rdx, rdi
0x1802332c4  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x1802332c9  mov     ebx, eax
0x1802332cb  test    eax, eax
0x1802332cd  jns     short loc_1802332D6
0x1802332cf  mov     edx, 14Ah
0x1802332d4  jmp     short loc_180233297
0x1802332d6  mov     [rbp+57h+var_B0], r15
0x1802332da  lea     rcx, [rbp+57h+var_B0]
0x1802332de  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802332e3  lea     r9, [rbp+57h+var_B0]; ppvOut
0x1802332e7  lea     r8, _GUID_0cd45e71_d927_4f15_8b0a_8fef525337bf; riid
0x1802332ee  lea     rdx, SID_VirtualDesktopNotificationService; guidService
0x1802332f5  mov     rcx, [r14+10h]; punk
0x1802332f9  call    cs:__imp_IUnknown_QueryService
0x1802332ff  test    eax, eax
0x180233301  js      short loc_180233347
0x180233303  lea     rcx, [rsi+38h]
0x180233307  mov     r9d, r12d
0x18023330a  mov     r8, [rbp+57h+var_B0]
0x18023330e  lea     rdx, _GUID_0cd45e71_d927_4f15_8b0a_8fef525337bf
0x180233315  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x18023331a  mov     ebx, eax
0x18023331c  test    eax, eax
0x18023331e  jns     short loc_180233347
0x180233320  mov     rcx, [rbp+5Fh]; this
0x180233324  mov     r9d, eax; char *
0x180233327  lea     r8, aPcshellTwinuiM_50; "pcshell\\twinui\\multitaskingview\\lib"...
0x18023332e  mov     edx, 14Fh; void *
0x180233333  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180233338  nop
0x180233339  lea     rcx, [rbp+57h+var_B0]
0x18023333d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180233342  jmp     loc_1802332AB
0x180233347  mov     [rbp+57h+var_A8], r15
0x18023334b  lea     rcx, [rbp+57h+var_A8]
0x18023334f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180233354  lea     r9, [rbp+57h+var_A8]; ppvOut
0x180233358  lea     r8, _GUID_103231ae_04cb_4e5e_b63d_e3ce47cd0f0a; riid
0x18023335f  lea     rdx, stru_1807A44E8; guidService
0x180233366  mov     rcx, [r14+10h]; punk
0x18023336a  call    cs:__imp_IUnknown_QueryService
0x180233370  mov     ebx, eax
0x180233372  test    eax, eax
0x180233374  jns     short loc_18023339A
0x180233376  mov     edx, 153h; void *
0x18023337b  lea     r8, aPcshellTwinuiM_50; "pcshell\\twinui\\multitaskingview\\lib"...
0x180233382  mov     r9d, eax; char *
0x180233385  mov     rcx, [rbp+5Fh]; this
0x180233389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18023338e  nop
0x18023338f  lea     rcx, [rbp+57h+var_A8]
0x180233393  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180233398  jmp     short loc_180233339
0x18023339a  lea     rcx, [rsi+40h]
0x18023339e  mov     r9d, r12d
0x1802333a1  mov     r8, [rbp+57h+var_A8]
0x1802333a5  lea     rdx, _GUID_103231ae_04cb_4e5e_b63d_e3ce47cd0f0a
0x1802333ac  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x1802333b1  mov     ebx, eax
0x1802333b3  test    eax, eax
0x1802333b5  jns     short loc_1802333BE
0x1802333b7  mov     edx, 154h
0x1802333bc  jmp     short loc_18023337B
0x1802333be  mov     [rbp+57h+var_A0], r15
0x1802333c2  mov     rdi, [r14+0C8h]
0x1802333c9  mov     rax, [rdi]
0x1802333cc  mov     rbx, [rax]
0x1802333cf  lea     rcx, [rbp+57h+var_A0]
0x1802333d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802333d8  lea     r8, [rbp+57h+var_A0]
0x1802333dc  lea     rdx, _GUID_6e7da126_f47e_4b81_b43f_e466cf325f58
0x1802333e3  mov     rcx, rdi
0x1802333e6  mov     rax, rbx
0x1802333e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802333ee  nop
0x1802333ef  lea     rcx, [rsi+48h]
0x1802333f3  mov     r9d, r12d
0x1802333f6  mov     r8, [rbp+57h+var_A0]
  ... truncated ...
```
