# ModuleHandler::ModuleCallback(_WINDIAG_CALLBACK_INFO const *,_WINDIAG_VALUE *)

- ea: `0x1800214d8`
- end: `0x1800221e6`
- name: `?ModuleCallback@ModuleHandler@@QEAAJPEBU_WINDIAG_CALLBACK_INFO@@PEAU_WINDIAG_VALUE@@@Z`
- size: `3342`
- prototype: `__int64 __fastcall(ModuleHandler *this, const struct _WINDIAG_CALLBACK_INFO *, struct _WINDIAG_VALUE *)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180023f60`

## callees

- `0x180003e10`
- `0x180003e34`
- `0x1800052fc`
- `0x1800066dc`
- `0x180009044`
- `0x18000f410`
- `0x18001741c`
- `0x180017b60`
- `0x18001997c`
- `0x18001a69c`
- `0x18001bf90`
- `0x18001c32c`
- `0x18001c6b4`
- `0x18001cbbc`
- `0x18001ccf8`
- `0x180020364`
- `0x1800208f8`
- `0x180020b44`
- `0x180020dc4`
- `0x1800214d8`
- `0x180023378`
- `0x180023438`
- `0x180023ba8`
- `0x180024748`
- `0x180029010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002170a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021787`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002180c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021946`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021952`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021a43`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021a4f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021ad7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021bc6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021cea`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021cf6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021f6b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002170a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021787`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002180c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021946`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021952`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021a43`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021a4f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021ad7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021bc6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021cea`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021cf6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021f6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002202a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002202a`

## string_xrefs

- `0x18002176b`: `/plugin/action`
- `0x180021c01`: `/onesettings/module_config`
- `0x180021cca`: `/onesettings/extra_config`

## pseudocode

```c
__int64 __fastcall ModuleHandler::ModuleCallback(
        ModuleHandler *this,
        const struct _WINDIAG_CALLBACK_INFO *a2,
        struct _WINDIAG_VALUE *a3)
{
  bool v4; // r15
  int v5; // eax
  unsigned int v6; // edi
  __int64 result; // rax
  int v8; // eax
  void *v9; // rsi
  char v10; // r13
  int v11; // eax
  volatile signed __int32 *v12; // rdi
  int v13; // eax
  HANDLE ProcessHeap; // rax
  __int64 v15; // rcx
  bool v16; // r15
  void *v17; // rdi
  int v18; // eax
  HANDLE v19; // rax
  __int64 v20; // rcx
  struct _WINDIAG_VALUE *v21; // r8
  bool v22; // r15
  void *v23; // rdi
  int v24; // eax
  HANDLE v25; // rax
  unsigned int v26; // edi
  __int64 v27; // rcx
  bool v28; // r15
  void *v29; // rdi
  int v30; // eax
  HANDLE v31; // rax
  unsigned int v32; // edi
  __int64 v33; // rcx
  bool v34; // r15
  void *v35; // rdi
  int v36; // eax
  HANDLE v37; // rax
  unsigned int v38; // edi
  __int64 v39; // rcx
  bool v40; // r15
  void *v41; // rdi
  int v42; // eax
  HANDLE v43; // rax
  unsigned int v44; // edi
  __int64 v45; // rcx
  bool v46; // r15
  void *v47; // rdi
  int v48; // eax
  HANDLE v49; // rax
  unsigned int v50; // edi
  __int64 v51; // rcx
  bool v52; // r15
  void *v53; // rdi
  int v54; // eax
  HANDLE v55; // rax
  unsigned int OneSettingsValue; // edi
  __int64 v57; // rcx
  bool v58; // di
  void *v59; // rbx
  int v60; // r14d
  HANDLE v61; // rax
  unsigned int TraceProfile; // ebx
  __int64 v63; // rax
  char v64; // bl
  ModuleHandler *v65; // rcx
  __int64 v66; // rax
  char v67; // bl
  __int64 v68; // rcx
  __int64 v69; // rax
  char v70; // bl
  __int64 v71; // rcx
  __int64 v72; // rax
  char v73; // bl
  __int64 v74; // rax
  char v75; // bl
  _DWORD *v76; // rax
  __int64 v77; // rax
  char v78; // bl
  __int64 v79; // rax
  char v80; // bl
  HLOCAL v81; // rax
  __int64 v82; // rax
  char v83; // bl
  __int64 v84; // rax
  bool v85; // di
  const char *v86; // r9
  int v87; // [rsp+20h] [rbp-A8h]
  int v88; // [rsp+20h] [rbp-A8h]
  int v89; // [rsp+20h] [rbp-A8h]
  LPVOID lpMem; // [rsp+30h] [rbp-98h] BYREF
  LPVOID v91[2]; // [rsp+38h] [rbp-90h] BYREF
  const winrt::hresult_error *v92; // [rsp+48h] [rbp-80h] BYREF
  int v93; // [rsp+50h] [rbp-78h] BYREF
  __int128 v94; // [rsp+58h] [rbp-70h]
  LPVOID v95; // [rsp+68h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  struct _WINDIAG_CALLBACK_INFO *v98; // [rsp+D8h] [rbp+10h] BYREF
  void *v99; // [rsp+E8h] [rbp+20h] BYREF

  v98 = a2;
  v4 = 0;
  LODWORD(v99) = 0;
  *(_OWORD *)a3 = 0;
  *((_QWORD *)a3 + 2) = 0;
  lpMem = 0;
  try
  {
    v5 = ConvertUTF8StringToWideString(*((LPCCH *)a2 + 1));
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21F,
        (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
        (const char *)(unsigned int)v5,
        v89);
      return v6;
    }
    v95 = lpMem;
    v91[0] = &v95;
    v91[1] = &qword_180034AD8;
    _InterlockedIncrement64(&qword_180034AD8);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> )
    {
      v99 = 0;
      v93 = 0;
      v94 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, LPVOID, void **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
                                                               + 48LL))(
             winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>,
             v95,
             &v99);
      if ( v8 < 0 )
        winrt::throw_hresult((unsigned int)v8, &v93);
      v9 = v99;
      _InterlockedAdd64(&qword_180034AD8, 0xFFFFFFFFFFFFFFFFuLL);
      v10 = 60;
    }
    else
    {
      _InterlockedAdd64(&qword_180034AD8, 0xFFFFFFFFFFFFFFFFuLL);
      winrt::impl::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::call<_lambda_0a61d549bec6c444b35123f4c9509ca7_ &>(
        0,
        &v99,
        v91);
      v10 = 36;
      v9 = v99;
    }
    v91[0] = 0;
    v93 = 0;
    v94 = 0;
    v11 = (*(__int64 (__fastcall **)(void *, LPVOID *))(*(_QWORD *)v9 + 136LL))(v9, v91);
    if ( v11 < 0 )
      winrt::throw_hresult((unsigned int)v11, &v93);
    v12 = (volatile signed __int32 *)v91[0];
    if ( v91[0] )
    {
      if ( *((_DWORD *)v91[0] + 1) == 8 )
        v4 = wmemcmp(*((const wchar_t **)v91[0] + 2), L"callback", 8u) == 0;
      v13 = _InterlockedDecrement(v12 + 6);
      if ( v13 )
      {
        if ( v13 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v12);
      }
    }
    if ( v4 )
    {
      v15 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Host(
                         &v99,
                         v91);
      v16 = v15 && *(_DWORD *)(v15 + 4) == 6 && wmemcmp(*(const wchar_t **)(v15 + 16), L"whesvc", 6u) == 0;
      v17 = v91[0];
      if ( v91[0] )
      {
        v18 = _InterlockedDecrement((volatile signed __int32 *)v91[0] + 6);
        if ( v18 )
        {
          if ( v18 < 0 )
            abort();
        }
        else
        {
          v19 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v19, 0, v17);
        }
      }
      if ( v16 )
      {
        v20 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(
                           &v99,
                           v91);
        v22 = v20
           && (v21 = (struct _WINDIAG_VALUE *)*(unsigned int *)(v20 + 4), v21 == (struct _WINDIAG_VALUE *)14)
           && wmemcmp(*(const wchar_t **)(v20 + 16), L"/plugin/action", 0xEu) == 0;
        v23 = v91[0];
        if ( v91[0] )
        {
          v24 = _InterlockedDecrement((volatile signed __int32 *)v91[0] + 6);
          if ( v24 )
          {
            if ( v24 < 0 )
              abort();
          }
          else
          {
            v25 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v25, 0, v23);
          }
        }
        if ( v22 )
        {
          v26 = ModuleHandler::ActionCallback((ModuleHandler *)v20, v98, v21);
          if ( v9 )
            winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v99);
          return v26;
        }
        v27 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(
                           &v99,
                           v91);
        v28 = v27 && *(_DWORD *)(v27 + 4) == 14 && wmemcmp(*(const wchar_t **)(v27 + 16), L"/invoke/module", 0xEu) == 0;
        v29 = v91[0];
        if ( v91[0] )
        {
          v30 = _InterlockedDecrement((volatile signed __int32 *)v91[0] + 6);
          if ( v30 )
          {
            if ( v30 < 0 )
              abort();
          }
          else
          {
            v31 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v31, 0, v29);
          }
        }
        if ( v28 )
        {
          v91[0] = v9;
          if ( v9 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 8LL))(v9);
          v32 = ModuleHandler::InvokeModule(v27, 0, (__int64)v98, v91);
          if ( v9 )
            winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v99);
          return v32;
        }
        v33 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(
                           &v99,
                           v91);
        v34 = v33
           && *(_DWORD *)(v33 + 4) == 18
           && wmemcmp(*(const wchar_t **)(v33 + 16), L"/queue/heavymodule", 0x12u) == 0;
        v35 = v91[0];
        if ( v91[0] )
        {
          v36 = _InterlockedDecrement((volatile signed __int32 *)v91[0] + 6);
          if ( v36 )
          {
            if ( v36 < 0 )
              abort();
          }
          else
          {
            v37 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v37, 0, v35);
          }
        }
        if ( v34 )
        {
          v91[0] = v9;
          if ( v9 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 8LL))(v9);
          v38 = ModuleHandler::InvokeModule(v33, 1, (__int64)v98, v91);
          if ( v9 )
            winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v99);
          return v38;
        }
        v39 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(
                           &v99,
                           v91);
        v40 = v39
           && *(_DWORD *)(v39 + 4) == 16
           && wmemcmp(*(const wchar_t **)(v39 + 16), L"/feature/enabled", 0x10u) == 0;
        v41 = v91[0];
        if ( v91[0] )
        {
          v42 = _InterlockedDecrement((volatile signed __int32 *)v91[0] + 6);
          if ( v42 )
          {
            if ( v42 < 0 )
              abort();
          }
          else
          {
            v43 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v43, 0, v41);
          }
        }
        if ( v40 )
        {
          v44 = ModuleHandler::FeatureEnabled((ModuleHandler *)v39, v98, a3);
          if ( v9 )
            winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v99);
          return v44;
        }
        v46 = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixesQ3>::GetImpl'::`2'::impl) )
        {
          v10 |= 1u;
          v45 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(
                             &v99,
                             v91);
          if ( v45 )
          {
            if ( *(_DWORD *)(v45 + 4) == 14 && !wmemcmp(*(const wchar_t **)(v45 + 16), L"/feature/names", 0xEu) )
              v46 = 1;
          }
        }
        if ( (v10 & 1) != 0 )
        {
          v47 = v91[0];
          if ( v91[0] )
          {
            v48 = _InterlockedDecrement((volatile signed __int32 *)v91[0] + 6);
            if ( v48 )
            {
              if ( v48 < 0 )
                abort();
            }
            else
            {
              v49 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v49, 0, v47);
            }
          }
        }
        if ( v46 )
        {
          v50 = ModuleHandler::FeatureNames((ModuleHandler *)v45, a3);
          if ( v9 )
            winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v99);
          return v50;
        }
        v51 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(
                           &v99,
                           v91);
        v52 = v51
           && *(_DWORD *)(v51 + 4) == 26
           && wmemcmp(*(const wchar_t **)(v51 + 16), L"/onesettings/module_config", 0x1Au) == 0;
        v53 = v91[0];
        if ( v91[0] )
        {
          v54 = _InterlockedDecrement((volatile signed __int32 *)v91[0] + 6);
          if ( v54 )
          {
            if ( v54 < 0 )
              abort();
          }
          else
          {
            v55 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v55, 0, v53);
          }
        }
        if ( v52 )
        {
          OneSettingsValue = ModuleHandler::GetOneSettingsValue((ModuleHandler *)v51, v98, L"WHESVC_MOD", a3);
          if ( v9 )
            winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v99);
          return OneSettingsValue;
        }
        v57 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(
                           &v99,
                           v91);
        v58 = v57
           && *(_DWORD *)(v57 + 4) == 25
           && wmemcmp(*(const wchar_t **)(v57 + 16), L"/onesettings/extra_config", 0x19u) == 0;
        v59 = v91[0];
        if ( v91[0] )
        {
          v60 = _InterlockedDecrement((volatile signed __int32 *)v91[0] + 6);
          if ( v60 )
          {
            if ( v60 < 0 )
              abort();
          }
          else
          {
            v61 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v61, 0, v59);
          }
        }
        if ( v58 )
        {
          TraceProfile = ModuleHandler::GetOneSettingsValue((ModuleHandler *)v57, v98, L"WHESVC_EXT", a3);
          if ( v9 )
            winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v99);
LABEL_148:
          winrt::hstring::~hstring((winrt::hstring *)&lpMem);
          return TraceProfile;
        }
        v63 = winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(
                &v99,
                v91);
        v64 = winrt::operator==(v63, L"/trace/profile");
        winrt::hstring::~hstring((winrt::hstring *)v91);
        if ( v64 )
        {
          TraceProfile = ModuleHandler::GetTraceProfile(v65, v98, a3);
          if ( v9 )
            winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v99);
          goto LABEL_148;
        }
        v66 = winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(
                &v99,
                v91);
        v67 = winrt::operator==(v66, L"/wnf/register");
        winrt::hstring::~hstring((winrt::hstring *)v91);
        if ( v67 )
        {
          v91[0] = v9;
          if ( v9 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 8LL))(v9);
          TraceProfile = ModuleHandler::RegisterWNF(v68, v91, v98);
          if ( v9 )
            winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v99);
          goto LABEL_148;
        }
        v69 = winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(
                &v99,
                &v98);
        v70 = winrt::operator==(v69, L"/wnf/unregister");
        winrt::hstring::~hstring((winrt::hstring *)&v98);
        if ( v70 )
        {
          v98 = (struct _WINDIAG_CALLBACK_INFO *)v9;
          if ( v9 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 8LL))(v9);
          TraceProfile = ModuleHandler::UnregisterWNF(v71, &v98);
          if ( v9 )
            winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v99);
          goto LABEL_148;
        }
        goto LABEL_170;
      }
      v72 = winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Host(
              &v99,
              v91);
      v73 = winrt::operator==(v72, L"windiag");
      winrt::hstring::~hstring((winrt::hstring *)v91);
      if ( v73 )
      {
        v74 = winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(
                &v99,
                v91);
        v75 = winrt::operator==(v74, L"/resume/delay");
        winrt::hstring::~hstring((winrt::hstring *)v91);
        if ( v75 )
        {
          v76 = (_DWORD *)*((_QWORD *)v98 + 2);
          if ( *v76 == 2 )
          {
            *((_DWORD *)this + 8) = v76[2];
            TraceProfile = 0;
          }
          else
          {
            TraceProfile = -2147024809;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x350,
              (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
              (const char *)0x80070057LL,
              v89);
          }
          if ( v9 )
            winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v99);
          goto LABEL_148;
        }
        goto LABEL_170;
      }
      v77 = winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Host(
              &v99,
              &v98);
      v78 = winrt::operator==(v77, L"system");
      winrt::hstring::~hstring((winrt::hstring *)&v98);
      if ( v78 )
      {
        v79 = winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(
                &v99,
                &v98);
        v80 = winrt::operator==(v79, L"/host/id");
        winrt::hstring::~hstring((winrt::hstring *)&v98);
        if ( v80 )
        {
          v81 = LocalAlloc(0x40u, 6u);
          *((_QWORD *)a3 + 1) = v81;
          if ( v81 )
          {
            qmemcpy(v81, "whesvc", 6);
            *((_DWORD *)a3 + 4) = 6;
            *(_DWORD *)a3 = 4;
          }
          if ( v9 )
            winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v99);
LABEL_169:
          winrt::hstring::~hstring((winrt::hstring *)&lpMem);
          return 0;
        }
        v82 = winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(
                &v99,
                &v98);
        v83 = winrt::operator==(v82, L"/load/library");
        winrt::hstring::~hstring((winrt::hstring *)&v98);
        if ( v83 )
        {
          *((_QWORD *)a3 + 1) = *(_QWORD *)AssetLoaderSingleton::GetInstance();
          *(_DWORD *)a3 = 2;
          if ( v9 )
            winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v99);
          goto LABEL_169;
        }
        v85 = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes2D>::GetImpl'::`2'::impl) )
        {
          v84 = winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(
                  &v99,
                  &v98);
          v10 |= 2u;
          if ( (unsigned __int8)winrt::operator==(v84, L"/module/heap") )
            v85 = 1;
        }
        if ( (v10 & 2) != 0 )
          winrt::hstring::~hstring((winrt::hstring *)&v98);
        if ( v85 )
        {
          *((_QWORD *)a3 + 1) = hHeap;
          *(_DWORD *)a3 = 2;
          if ( v9 )
            winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v99);
          goto LABEL_169;
        }
      }
    }
LABEL_170:
    if ( v9 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v99);
    winrt::hstring::~hstring((winrt::hstring *)&lpMem);
    result = 2147943568LL;
  }
  catch ( const winrt::hresult_error *v92 )
  {
    v86 = (const char *)*((unsigned int *)v92 + 3);
    LODWORD(v98) = (_DWORD)v86;
    if ( (int)v86 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26D,
        (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
        v86,
        v88);
    return (unsigned int)v98;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x271,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
      (const char *)0x80004005LL,
      v87);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800214d8  mov     [rsp+arg_8], rdx
0x1800214dd  mov     [rsp+arg_0], rcx
0x1800214e2  push    rbx
0x1800214e3  push    rsi
0x1800214e4  push    rdi
0x1800214e5  push    r12
0x1800214e7  push    r13
0x1800214e9  push    r14
0x1800214eb  push    r15
0x1800214ed  sub     rsp, 90h
0x1800214f4  mov     r12, r8
0x1800214f7  mov     rax, rdx
0x1800214fa  xor     r15d, r15d
0x1800214fd  mov     dword ptr [rsp+0C8h+arg_18], r15d
0x180021505  xorps   xmm0, xmm0
0x180021508  xor     ecx, ecx
0x18002150a  movups  xmmword ptr [r8], xmm0
0x18002150e  mov     [r8+10h], rcx
0x180021512  mov     [rsp+0C8h+lpMem], r15
0x180021517  lea     rdx, [rsp+0C8h+lpMem]
0x18002151c  mov     rcx, [rax+8]; lpMultiByteStr
0x180021520  call    ConvertUTF8StringToWideString
0x180021525  mov     edi, eax
0x180021527  test    eax, eax
0x180021529  jns     short loc_180021587
0x18002152b  mov     rcx, [rsp+0C8h]; this
0x180021533  mov     r9d, eax; char *
0x180021536  lea     r8, aPcshellBaseWhe_2; "pcshell\\base\\whesvc\\lib\\modulehandl"...
0x18002153d  mov     edx, 21Fh; void *
0x180021542  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021547  nop
0x180021548  mov     rbx, [rsp+0C8h+lpMem]
0x18002154d  test    rbx, rbx
0x180021550  jz      short loc_180021580
0x180021552  or      r14, 0FFFFFFFFFFFFFFFFh
0x180021556  lock xadd [rbx+18h], r14d
0x18002155c  sub     r14d, 1
0x180021560  jnz     short loc_180021577
0x180021562  nop
0x180021563  call    WINRT_IMPL_GetProcessHeap
0x180021568  mov     rcx, rax; hHeap
0x18002156b  mov     r8, rbx; lpMem
0x18002156e  xor     edx, edx; dwFlags
0x180021570  call    WINRT_IMPL_HeapFree
0x180021575  jmp     short loc_180021580
0x180021577  test    r14d, r14d
0x18002157a  js      loc_180021CF6
0x180021580  mov     eax, edi
0x180021582  jmp     loc_1800221B8
0x180021587  mov     rbx, [rsp+0C8h+lpMem]
0x18002158c  mov     [rsp+0C8h+var_60], rbx
0x180021591  lea     rax, [rsp+0C8h+var_60]
0x180021596  mov     [rsp+0C8h+var_90], rax
0x18002159b  lea     rax, qword_180034AD8
0x1800215a2  mov     [rsp+0C8h+var_88], rax
0x1800215a7  lock inc cs:qword_180034AD8
0x1800215af  mov     rcx, cs:??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x1800215b6  test    rcx, rcx
0x1800215b9  jz      short loc_180021614
0x1800215bb  mov     [rsp+0C8h+arg_18], r15
0x1800215c3  mov     [rsp+0C8h+var_78], r15d
0x1800215c8  xorps   xmm0, xmm0
0x1800215cb  movdqu  [rsp+0C8h+var_70], xmm0
0x1800215d1  mov     rax, [rcx]
0x1800215d4  lea     r8, [rsp+0C8h+arg_18]
0x1800215dc  mov     rdx, [rsp+0C8h+var_60]
0x1800215e1  mov     rax, [rax+30h]
0x1800215e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215ea  test    eax, eax
0x1800215ec  js      loc_1800221CB
0x1800215f2  mov     rsi, [rsp+0C8h+arg_18]
0x1800215fa  mov     [rsp+0C8h+arg_18], rsi
0x180021602  or      r14, 0FFFFFFFFFFFFFFFFh
0x180021606  lock add cs:qword_180034AD8, r14
0x18002160e  lea     r13d, [r14+3Dh]
0x180021612  jmp     short loc_18002163E
0x180021614  or      r14, 0FFFFFFFFFFFFFFFFh
0x180021618  lock add cs:qword_180034AD8, r14
0x180021620  lea     r8, [rsp+0C8h+var_90]
0x180021625  lea     rdx, [rsp+0C8h+arg_18]
0x18002162d  call    ??$call@AEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@QEAA?A_PAEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@Z
0x180021632  lea     r13d, [r14+25h]
0x180021636  mov     rsi, [rsp+0C8h+arg_18]
0x18002163e  mov     [rsp+0C8h+var_90], r15
0x180021643  mov     [rsp+0C8h+var_78], r15d
0x180021648  xorps   xmm0, xmm0
0x18002164b  movdqu  [rsp+0C8h+var_70], xmm0
0x180021651  mov     rax, [rsi]
0x180021654  lea     rdx, [rsp+0C8h+var_90]
0x180021659  mov     rcx, rsi
0x18002165c  mov     rax, [rax+88h]
0x180021663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021668  test    eax, eax
0x18002166a  js      loc_1800221D8
0x180021670  mov     rdi, [rsp+0C8h+var_90]
0x180021675  test    rdi, rdi
0x180021678  jz      short loc_1800216C1
0x18002167a  mov     r8d, [rdi+4]; N
0x18002167e  cmp     r8, 8
0x180021682  jnz     short loc_18002169C
0x180021684  lea     rdx, aCallback; "callback"
0x18002168b  mov     rcx, [rdi+10h]; S1
0x18002168f  call    wmemcmp
0x180021694  test    eax, eax
0x180021696  setz    r15b
0x18002169a  jmp     short loc_1800216A1
0x18002169c  test    rdi, rdi
0x18002169f  jz      short loc_1800216C1
0x1800216a1  mov     eax, r14d
0x1800216a4  lock xadd [rdi+18h], eax
0x1800216a9  sub     eax, 1
0x1800216ac  jnz     short loc_180021706
0x1800216ae  nop
0x1800216af  call    WINRT_IMPL_GetProcessHeap
0x1800216b4  mov     rcx, rax; hHeap
0x1800216b7  mov     r8, rdi; lpMem
0x1800216ba  xor     edx, edx; dwFlags
0x1800216bc  call    WINRT_IMPL_HeapFree
0x1800216c1  test    r15b, r15b
0x1800216c4  jz      loc_180022185
0x1800216ca  lea     rdx, [rsp+0C8h+var_90]
0x1800216cf  lea     rcx, [rsp+0C8h+arg_18]
0x1800216d7  call    ?Host@?$consume_Windows_Foundation_IUriRuntimeClass@UIUriRuntimeClass@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Host(void)
0x1800216dc  mov     rcx, [rax]
0x1800216df  test    rcx, rcx
0x1800216e2  jz      short loc_180021711
0x1800216e4  mov     r8d, [rcx+4]; N
0x1800216e8  cmp     r8, 6
0x1800216ec  jnz     short loc_180021711
0x1800216ee  lea     rdx, aWhesvc_0; "whesvc"
0x1800216f5  mov     rcx, [rcx+10h]; S1
0x1800216f9  call    wmemcmp
0x1800216fe  test    eax, eax
0x180021700  setz    r15b
0x180021704  jmp     short loc_180021714
0x180021706  test    eax, eax
0x180021708  jns     short loc_1800216C1
0x18002170a  call    cs:__imp_abort
0x180021711  xor     r15b, r15b
0x180021714  mov     rdi, [rsp+0C8h+var_90]
0x180021719  test    rdi, rdi
0x18002171c  jz      short loc_18002173E
0x18002171e  mov     eax, r14d
0x180021721  lock xadd [rdi+18h], eax
0x180021726  sub     eax, 1
0x180021729  jnz     short loc_180021783
0x18002172b  nop
0x18002172c  call    WINRT_IMPL_GetProcessHeap
0x180021731  mov     rcx, rax; hHeap
0x180021734  mov     r8, rdi; lpMem
0x180021737  xor     edx, edx; dwFlags
0x180021739  call    WINRT_IMPL_HeapFree
0x18002173e  lea     rdx, [rsp+0C8h+var_90]
0x180021743  lea     rcx, [rsp+0C8h+arg_18]
0x18002174b  test    r15b, r15b
0x18002174e  jz      loc_180021EE2
0x180021754  call    ?Path@?$consume_Windows_Foundation_IUriRuntimeClass@UIUriRuntimeClass@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(void)
0x180021759  mov     rcx, [rax]
0x18002175c  test    rcx, rcx
0x18002175f  jz      short loc_18002178E
0x180021761  mov     r8d, [rcx+4]; N
0x180021765  cmp     r8, 0Eh
0x180021769  jnz     short loc_18002178E
0x18002176b  lea     rdx, aPluginAction; "/plugin/action"
0x180021772  mov     rcx, [rcx+10h]; S1
0x180021776  call    wmemcmp
0x18002177b  test    eax, eax
0x18002177d  setz    r15b
0x180021781  jmp     short loc_180021791
0x180021783  test    eax, eax
0x180021785  jns     short loc_18002173E
0x180021787  call    cs:__imp_abort
0x18002178e  xor     r15b, r15b
0x180021791  mov     rdi, [rsp+0C8h+var_90]
0x180021796  test    rdi, rdi
0x180021799  jz      short loc_1800217BB
0x18002179b  mov     eax, r14d
0x18002179e  lock xadd [rdi+18h], eax
0x1800217a3  sub     eax, 1
0x1800217a6  jnz     short loc_180021808
0x1800217a8  nop
0x1800217a9  call    WINRT_IMPL_GetProcessHeap
0x1800217ae  mov     rcx, rax; hHeap
0x1800217b1  mov     r8, rdi; lpMem
0x1800217b4  xor     edx, edx; dwFlags
0x1800217b6  call    WINRT_IMPL_HeapFree
0x1800217bb  test    r15b, r15b
0x1800217be  jz      short loc_180021823
0x1800217c0  mov     rdx, [rsp+0C8h+arg_8]; struct _WINDIAG_CALLBACK_INFO *
0x1800217c8  call    ?ActionCallback@ModuleHandler@@AEAAJPEBU_WINDIAG_CALLBACK_INFO@@PEAU_WINDIAG_VALUE@@@Z; ModuleHandler::ActionCallback(_WINDIAG_CALLBACK_INFO const *,_WINDIAG_VALUE *)
0x1800217cd  mov     edi, eax
0x1800217cf  test    rsi, rsi
0x1800217d2  jz      short loc_1800217E2
0x1800217d4  lea     rcx, [rsp+0C8h+arg_18]
0x1800217dc  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800217e1  nop
0x1800217e2  test    rbx, rbx
0x1800217e5  jz      short loc_18002181C
0x1800217e7  lock xadd [rbx+18h], r14d
0x1800217ed  sub     r14d, 1
0x1800217f1  jnz     short loc_180021813
0x1800217f3  nop
0x1800217f4  call    WINRT_IMPL_GetProcessHeap
0x1800217f9  mov     rcx, rax; hHeap
0x1800217fc  mov     r8, rbx; lpMem
0x1800217ff  xor     edx, edx; dwFlags
0x180021801  call    WINRT_IMPL_HeapFree
0x180021806  jmp     short loc_18002181C
0x180021808  test    eax, eax
0x18002180a  jns     short loc_1800217BB
0x18002180c  call    cs:__imp_abort
0x180021813  test    r14d, r14d
0x180021816  js      loc_180021CF6
0x18002181c  mov     eax, edi
0x18002181e  jmp     loc_1800221B8
0x180021823  lea     rdx, [rsp+0C8h+var_90]
0x180021828  lea     rcx, [rsp+0C8h+arg_18]
0x180021830  call    ?Path@?$consume_Windows_Foundation_IUriRuntimeClass@UIUriRuntimeClass@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(void)
0x180021835  mov     rcx, [rax]
0x180021838  test    rcx, rcx
0x18002183b  jz      short loc_18002185F
0x18002183d  mov     r8d, [rcx+4]; N
0x180021841  cmp     r8, 0Eh
0x180021845  jnz     short loc_18002185F
0x180021847  lea     rdx, aInvokeModule; "/invoke/module"
0x18002184e  mov     rcx, [rcx+10h]; S1
0x180021852  call    wmemcmp
0x180021857  test    eax, eax
0x180021859  setz    r15b
0x18002185d  jmp     short loc_180021862
0x18002185f  xor     r15b, r15b
0x180021862  mov     rdi, [rsp+0C8h+var_90]
0x180021867  test    rdi, rdi
0x18002186a  jz      short loc_180021890
0x18002186c  mov     eax, r14d
0x18002186f  lock xadd [rdi+18h], eax
0x180021874  sub     eax, 1
0x180021877  jnz     loc_18002193E
0x18002187d  nop
0x18002187e  call    WINRT_IMPL_GetProcessHeap
0x180021883  mov     rcx, rax; hHeap
0x180021886  mov     r8, rdi; lpMem
0x180021889  xor     edx, edx; dwFlags
0x18002188b  call    WINRT_IMPL_HeapFree
0x180021890  test    r15b, r15b
0x180021893  jz      short loc_180021902
0x180021895  mov     [rsp+0C8h+var_90], rsi
0x18002189a  test    rsi, rsi
0x18002189d  jz      short loc_1800218AE
0x18002189f  mov     rax, [rsi]
0x1800218a2  mov     rcx, rsi
0x1800218a5  mov     rax, [rax+8]
0x1800218a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218ae  lea     r9, [rsp+0C8h+var_90]
0x1800218b3  mov     r8, [rsp+0C8h+arg_8]
0x1800218bb  xor     edx, edx
0x1800218bd  call    ?InvokeModule@ModuleHandler@@AEAAJ_NPEBU_WINDIAG_CALLBACK_INFO@@UUri@Foundation@Windows@winrt@@PEAU_WINDIAG_VALUE@@@Z; ModuleHandler::InvokeModule(bool,_WINDIAG_CALLBACK_INFO const *,winrt::Windows::Foundation::Uri,_WINDIAG_VALUE *)
0x1800218c2  mov     edi, eax
0x1800218c4  test    rsi, rsi
0x1800218c7  jz      short loc_1800218D7
0x1800218c9  lea     rcx, [rsp+0C8h+arg_18]
0x1800218d1  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800218d6  nop
0x1800218d7  test    rbx, rbx
0x1800218da  jz      short loc_1800218FB
0x1800218dc  lock xadd [rbx+18h], r14d
0x1800218e2  sub     r14d, 1
0x1800218e6  jnz     short loc_18002194D
0x1800218e8  nop
0x1800218e9  call    WINRT_IMPL_GetProcessHeap
0x1800218ee  mov     rcx, rax; hHeap
0x1800218f1  mov     r8, rbx; lpMem
0x1800218f4  xor     edx, edx; dwFlags
0x1800218f6  call    WINRT_IMPL_HeapFree
0x1800218fb  mov     eax, edi
0x1800218fd  jmp     loc_1800221B8
0x180021902  lea     rdx, [rsp+0C8h+var_90]
0x180021907  lea     rcx, [rsp+0C8h+arg_18]
0x18002190f  call    ?Path@?$consume_Windows_Foundation_IUriRuntimeClass@UIUriRuntimeClass@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(void)
0x180021914  mov     rcx, [rax]
0x180021917  test    rcx, rcx
0x18002191a  jz      short loc_180021959
0x18002191c  mov     r8d, [rcx+4]; N
0x180021920  cmp     r8, 12h
0x180021924  jnz     short loc_180021959
0x180021926  lea     rdx, aQueueHeavymodu; "/queue/heavymodule"
0x18002192d  mov     rcx, [rcx+10h]; S1
0x180021931  call    wmemcmp
0x180021936  test    eax, eax
0x180021938  setz    r15b
0x18002193c  jmp     short loc_18002195C
0x18002193e  test    eax, eax
0x180021940  jns     loc_180021890
0x180021946  call    cs:__imp_abort
0x18002194d  test    r14d, r14d
0x180021950  jns     short loc_1800218FB
0x180021952  call    cs:__imp_abort
0x180021959  xor     r15b, r15b
0x18002195c  mov     rdi, [rsp+0C8h+var_90]
0x180021961  test    rdi, rdi
  ... truncated ...
```
