# MSATokenBroker::VerifyUserAccount(wpc::MicrosoftAccount::AuthScope const &,HWND__ *)

- ea: `0x14007de14`
- end: `0x14007eb2e`
- name: `?VerifyUserAccount@MSATokenBroker@@YAJAEBVAuthScope@MicrosoftAccount@wpc@@PEAUHWND__@@@Z`
- size: `3354`
- prototype: `__int64 __fastcall(MSATokenBroker *__hidden this, const struct wpc::MicrosoftAccount::AuthScope *, HWND)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400571d0`

## callees

- `0x140005530`
- `0x140016854`
- `0x140031ba0`
- `0x140079a50`
- `0x140079ac8`
- `0x14007a2e0`
- `0x14007b090`
- `0x14007de14`
- `0x14007eb34`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007de65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007df06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007e096`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007de65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007df06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007e096`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14007de9f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14007e0d0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14007de9f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14007e0d0`

## string_xrefs

- `0x14007deb2`: `shellcommon\shell\wpccore\corelib\msatokenbroker.cpp`
- `0x14007df35`: `shellcommon\shell\wpccore\corelib\msatokenbroker.cpp`
- `0x14007df9e`: `shellcommon\shell\wpccore\corelib\msatokenbroker.cpp`
- `0x14007e015`: `shellcommon\shell\wpccore\corelib\msatokenbroker.cpp`
- `0x14007e0e7`: `shellcommon\shell\wpccore\corelib\msatokenbroker.cpp`
- `0x14007e1de`: `shellcommon\shell\wpccore\corelib\msatokenbroker.cpp`
- `0x14007e2bf`: `shellcommon\shell\wpccore\corelib\msatokenbroker.cpp`
- `0x14007e3ae`: `shellcommon\shell\wpccore\corelib\msatokenbroker.cpp`
- `0x14007e4db`: `shellcommon\shell\wpccore\corelib\msatokenbroker.cpp`
- `0x14007e5da`: `shellcommon\shell\wpccore\corelib\msatokenbroker.cpp`
- `0x14007e71e`: `shellcommon\shell\wpccore\corelib\msatokenbroker.cpp`
- `0x14007e82b`: `shellcommon\shell\wpccore\corelib\msatokenbroker.cpp`
- `0x14007ea0a`: `shellcommon\shell\wpccore\corelib\msatokenbroker.cpp`
- `0x14007de5e`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x14007e08f`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall MSATokenBroker::VerifyUserAccount(
        MSATokenBroker *this,
        const struct wpc::MicrosoftAccount::AuthScope *a2,
        HWND a3)
{
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  int ActivationFactory; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  _QWORD *v11; // rbx
  __int64 (__fastcall **v12)(_QWORD *, GUID *, _QWORD *); // rsi
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  int v16; // eax
  __int64 v17; // rcx
  _QWORD *v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  _QWORD *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  _QWORD *v25; // rcx
  HRESULT v26; // eax
  int v27; // edx
  unsigned int v28; // r8d
  HSTRING v29; // rbx
  __int64 v30; // rcx
  int v31; // eax
  unsigned int v32; // r8d
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  _QWORD *v36; // rcx
  __int64 v37; // rbx
  __int64 (__fastcall *v38)(__int64, __int64, PVOID, PVOID); // r14
  PVOID Reserved1; // rsi
  unsigned int v40; // r8d
  HSTRING_HEADER *v41; // rax
  int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  _QWORD *v47; // rcx
  int v48; // eax
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  _QWORD *v54; // rcx
  int v55; // eax
  HRESULT v56; // edx
  __int64 v57; // r8
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  _QWORD *v64; // rcx
  __int64 v65; // rdi
  int v66; // eax
  __int64 v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  _QWORD *v74; // rcx
  __int64 v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  _QWORD *v82; // rcx
  bool v83; // sf
  const WCHAR *v84; // rcx
  __int64 v85; // rcx
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  __int64 v90; // rcx
  __int64 v91; // rcx
  _QWORD *v92; // rcx
  const WCHAR *v93; // rcx
  __int64 v94; // rcx
  __int64 v95; // rcx
  __int64 v96; // rcx
  __int64 v97; // rcx
  __int64 v98; // rcx
  __int64 v99; // rcx
  __int64 v100; // rcx
  _QWORD *v101; // rcx
  __int64 v102; // rcx
  __int64 v103; // rcx
  __int64 v104; // rcx
  __int64 v105; // rcx
  __int64 v106; // rcx
  __int64 v107; // rcx
  __int64 v108; // rcx
  _QWORD *v109; // rcx
  __int64 v111; // rcx
  __int64 v112; // rcx
  __int64 v113; // rcx
  __int64 v114; // rcx
  __int64 v115; // rcx
  __int64 v116; // rcx
  __int64 v117; // rcx
  _QWORD *v118; // rcx
  int v119; // [rsp+20h] [rbp-89h]
  _QWORD *v120; // [rsp+40h] [rbp-69h] BYREF
  __int64 v121; // [rsp+48h] [rbp-61h] BYREF
  __int64 v122; // [rsp+50h] [rbp-59h] BYREF
  __int64 v123; // [rsp+58h] [rbp-51h] BYREF
  __int64 v124; // [rsp+60h] [rbp-49h] BYREF
  __int64 v125; // [rsp+68h] [rbp-41h] BYREF
  int v126[2]; // [rsp+70h] [rbp-39h] BYREF
  __int64 v127; // [rsp+78h] [rbp-31h] BYREF
  const WCHAR *v128; // [rsp+80h] [rbp-29h] BYREF
  int v129; // [rsp+88h] [rbp-21h] BYREF
  _DWORD v130[7]; // [rsp+8Ch] [rbp-1Dh] BYREF
  HSTRING string; // [rsp+A8h] [rbp-1h] BYREF
  HSTRING_HEADER v132; // [rsp+B0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v120 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(
         L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
         0x45u,
         (HSTRING_HEADER *)&v130[1],
         &string);
  if ( v5 < 0 )
    goto LABEL_207;
  ActivationFactory = RoGetActivationFactory(string, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v120);
  v9 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16A,
      (unsigned int)"shellcommon\\shell\\wpccore\\corelib\\msatokenbroker.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v119);
    v10 = v120;
    if ( v120 )
    {
      v120 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
    }
    return v9;
  }
  v121 = 0;
  v11 = v120;
  v12 = (__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD *))*v120;
  string = 0;
  v13 = WindowsCreateStringReference(L"https://login.windows.local", 0x1Bu, (HSTRING_HEADER *)&v130[1], &string);
  if ( v13 < 0 )
  {
LABEL_208:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
    JUMPOUT(0x14007EB2DLL);
  }
  v16 = v12[11](v11, (GUID *)string, &v121);
  v9 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16E,
      (unsigned int)"shellcommon\\shell\\wpccore\\corelib\\msatokenbroker.cpp",
      (const char *)(unsigned int)v16,
      v119);
    v17 = v121;
    if ( v121 )
    {
      v121 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v120;
    if ( v120 )
    {
      v120 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
    }
    return v9;
  }
  v122 = 0;
  v19 = BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(
          v121,
          &v122);
  v9 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"shellcommon\\shell\\wpccore\\corelib\\msatokenbroker.cpp",
      (const char *)(unsigned int)v19,
      v119);
    v20 = v122;
    if ( v122 )
    {
      v122 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = v121;
    if ( v121 )
    {
      v121 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = v120;
    if ( v120 )
    {
      v120 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
    }
    return v9;
  }
  if ( !v122 )
  {
    v9 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x172,
      (unsigned int)"shellcommon\\shell\\wpccore\\corelib\\msatokenbroker.cpp",
      (const char *)0x80004003LL,
      v119);
    v23 = v122;
    if ( v122 )
    {
      v122 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = v121;
    if ( v121 )
    {
      v121 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = v120;
    if ( v120 )
    {
      v120 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v25 + 16LL))(v25);
    }
    return v9;
  }
  v123 = 0;
  string = 0;
  v26 = WindowsCreateStringReference(
          L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
          0x38u,
          (HSTRING_HEADER *)&v130[1],
          &string);
  if ( v26 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v26, v27, v28);
LABEL_207:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    goto LABEL_208;
  }
  v29 = string;
  v30 = v123;
  if ( v123 )
  {
    v123 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = RoGetActivationFactory(v29, &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9, &v123);
  v9 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x175,
      (unsigned int)"shellcommon\\shell\\wpccore\\corelib\\msatokenbroker.cpp",
      (const char *)(unsigned int)v31,
      v119);
    v33 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    v34 = v122;
    if ( v122 )
    {
      v122 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v35 = v121;
    if ( v121 )
    {
      v121 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v36 = v120;
    if ( v120 )
    {
      v120 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
    }
    return v9;
  }
  v124 = 0;
  v37 = v123;
  v38 = *(__int64 (__fastcall **)(__int64, __int64, PVOID, PVOID))(*(_QWORD *)v123 + 56LL);
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                (HSTRING_HEADER *)&v130[1],
                (const WCHAR **)off_1400B0B00,
                v32)[1].Reserved.Reserved1;
  if ( *((_QWORD *)this + 3) > 7u )
    this = *(MSATokenBroker **)this;
  v128 = (const WCHAR *)this;
  v41 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v132, &v128, v40);
  v42 = v38(v37, v122, v41[1].Reserved.Reserved1, Reserved1);
  v9 = v42;
  if ( v42 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17C,
      (unsigned int)"shellcommon\\shell\\wpccore\\corelib\\msatokenbroker.cpp",
      (const char *)(unsigned int)v42,
      1);
    v43 = v124;
    if ( v124 )
    {
      v124 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
    v44 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    v45 = v122;
    if ( v122 )
    {
      v122 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
    v46 = v121;
    if ( v121 )
    {
      v121 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    v47 = v120;
    if ( v120 )
    {
      v120 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
    }
    return v9;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_49666091>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_49666091>::GetImpl'::`2'::impl) )
    Private::AddSsoPropertyToWebRequest(&v124);
  v125 = 0;
  v48 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v120)(
          v120,
          &GUID_f4b8e804_811e_4436_b69c_44cb67b72084,
          &v125);
  v9 = v48;
  if ( v48 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x184,
      (unsigned int)"shellcommon\\shell\\wpccore\\corelib\\msatokenbroker.cpp",
      (const char *)(unsigned int)v48,
      1);
    v49 = v125;
    if ( v125 )
    {
      v125 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    }
    v50 = v124;
    if ( v124 )
    {
      v124 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    v51 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    v52 = v122;
    if ( v122 )
    {
      v122 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
    v53 = v121;
    if ( v121 )
    {
      v121 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    }
    v54 = v120;
    if ( v120 )
    {
      v120 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v54 + 16LL))(v54);
    }
    return v9;
  }
  *(_QWORD *)v126 = 0;
  v55 = (*(__int64 (__fastcall **)(__int64, const struct wpc::MicrosoftAccount::AuthScope *, __int64, GUID *))(*(_QWORD *)v125 + 48LL))(
          v125,
          a2,
          v124,
          &GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9);
  v9 = v55;
  if ( v55 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18A,
      (unsigned int)"shellcommon\\shell\\wpccore\\corelib\\msatokenbroker.cpp",
      (const char *)(unsigned int)v55,
      (int)v126);
    v58 = *(_QWORD *)v126;
    if ( *(_QWORD *)v126 )
    {
      *(_QWORD *)v126 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    }
    v59 = v125;
    if ( v125 )
    {
      v125 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
    v60 = v124;
    if ( v124 )
    {
      v124 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    }
    v61 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    }
    v62 = v122;
    if ( v122 )
    {
      v122 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    }
    v63 = v121;
    if ( v121 )
    {
      v121 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    }
    v64 = v120;
    if ( v120 )
    {
      v120 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v64 + 16LL))(v64);
    }
    return v9;
  }
  v127 = 0;
  v65 = *(_QWORD *)v126;
  v9 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(
         *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))v126,
         v56,
         v57);
  if ( (v9 & 0x80000000) != 0
    || (v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v65 + 64LL))(v65, &v127), (v9 & 0x80000000) != 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18D,
      (unsigned int)"shellcommon\\shell\\wpccore\\corelib\\msatokenbroker.cpp",
      (const char *)v9,
      (int)v126);
    v111 = v127;
    if ( v127 )
    {
      v127 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
    }
    v112 = *(_QWORD *)v126;
    if ( *(_QWORD *)v126 )
    {
      *(_QWORD *)v126 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
    }
    v113 = v125;
    if ( v125 )
    {
      v125 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
    }
    v114 = v124;
    if ( v124 )
    {
      v124 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v114 + 16LL))(v114);
    }
    v115 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v115 + 16LL))(v115);
    }
    v116 = v122;
    if ( v122 )
    {
      v122 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v116 + 16LL))(v116);
    }
    v117 = v121;
    if ( v121 )
    {
      v121 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v117 + 16LL))(v117);
    }
    v118 = v120;
    if ( v120 )
    {
      v120 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v118 + 16LL))(v118);
    }
    return v9;
  }
  v129 = 0;
  v66 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v127 + 56LL))(v127, &v129);
  v9 = v66;
  if ( v66 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x190,
      (unsigned int)"shellcommon\\shell\\wpccore\\corelib\\msatokenbroker.cpp",
      (const char *)(unsigned int)v66,
      (int)v126);
    v67 = v127;
    if ( v127 )
    {
      v127 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    }
    v68 = *(_QWORD *)v126;
    if ( *(_QWORD *)v126 )
    {
      *(_QWORD *)v126 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    }
    v69 = v125;
    if ( v125 )
    {
      v125 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    }
    v70 = v124;
    if ( v124 )
    {
      v124 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
    }
    v71 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
    }
    v72 = v122;
    if ( v122 )
    {
      v122 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    }
    v73 = v121;
    if ( v121 )
    {
      v121 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
    }
    v74 = v120;
    if ( v120 )
    {
      v120 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v74 + 16LL))(v74);
    }
    return v9;
  }
  if ( v129 == 1 )
  {
    v9 = -2147023673;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x194,
      (unsigned int)"shellcommon\\shell\\wpccore\\corelib\\msatokenbroker.cpp",
      (const char *)0x800704C7LL,
      (int)v126);
    v75 = v127;
    if ( v127 )
    {
      v127 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
    }
    v76 = *(_QWORD *)v126;
    if ( *(_QWORD *)v126 )
    {
      *(_QWORD *)v126 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    }
    v77 = v125;
    if ( v125 )
    {
      v125 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    }
    v78 = v124;
    if ( v124 )
    {
      v124 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
    }
    v79 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
    }
    v80 = v122;
    if ( v122 )
    {
      v122 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    }
    v81 = v121;
    if ( v121 )
    {
      v121 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
    }
    v82 = v120;
    if ( v120 )
    {
      v120 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v82 + 16LL))(v82);
    }
    return v9;
  }
  if ( v129 )
  {
    v130[0] = 0;
    v128 = 0;
    if ( (*(int (__fastcall **)(__int64, const WCHAR **))(*(_QWORD *)v127 + 64LL))(v127, &v128) >= 0 )
      (*(void (__fastcall **)(const WCHAR *, _DWORD *))(*(_QWORD *)v128 + 48LL))(v128, v130);
    v9 = v130[0];
    v83 = v130[0] < 0;
    if ( v130[0] )
    {
      if ( v130[0] > 0 )
      {
        v9 = LOWORD(v130[0]) | 0x80070000;
        v83 = 1;
      }
      if ( v83 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A0,
          (unsigned int)"shellcommon\\shell\\wpccore\\corelib\\msatokenbroker.cpp",
          (const char *)v9,
          (int)v126);
      v84 = v128;
      if ( v128 )
      {
        v128 = 0;
        (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v84 + 16LL))(v84);
      }
      v85 = v127;
      if ( v127 )
      {
        v127 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
      }
      v86 = *(_QWORD *)v126;
      if ( *(_QWORD *)v126 )
      {
        *(_QWORD *)v126 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
      }
      v87 = v125;
      if ( v125 )
      {
        v125 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
      }
      v88 = v124;
      if ( v124 )
      {
        v124 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      }
      v89 = v123;
      if ( v123 )
      {
        v123 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
      }
      v90 = v122;
      if ( v122 )
      {
        v122 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
      }
      v91 = v121;
      if ( v121 )
      {
        v121 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      }
      v92 = v120;
      if ( v120 )
      {
        v120 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v92 + 16LL))(v92);
      }
    }
    else
    {
      v9 = -2147467259;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A2,
        (unsigned int)"shellcommon\\shell\\wpccore\\corelib\\msatokenbroker.cpp",
        (const char *)0x80004005LL,
        (int)v126);
      v93 = v128;
      if ( v128 )
      {
        v128 = 0;
        (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v93 + 16LL))(v93);
      }
      v94 = v127;
      if ( v127 )
      {
        v127 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      }
      v95 = *(_QWORD *)v126;
      if ( *(_QWORD *)v126 )
      {
        *(_QWORD *)v126 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
      }
      v96 = v125;
      if ( v125 )
      {
        v125 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
      }
      v97 = v124;
      if ( v124 )
      {
        v124 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
      }
      v98 = v123;
      if ( v123 )
      {
        v123 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
      }
      v99 = v122;
      if ( v122 )
      {
        v122 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
      }
      v100 = v121;
      if ( v121 )
      {
        v121 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 16LL))(v100);
      }
      v101 = v120;
      if ( v120 )
      {
        v120 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v101 + 16LL))(v101);
      }
    }
    return v9;
  }
  v102 = v127;
  if ( v127 )
  {
    v127 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v102 + 16LL))(v102);
  }
  v103 = *(_QWORD *)v126;
  if ( *(_QWORD *)v126 )
  {
    *(_QWORD *)v126 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
  }
  v104 = v125;
  if ( v125 )
  {
    v125 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
  }
  v105 = v124;
  if ( v124 )
  {
    v124 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
  }
  v106 = v123;
  if ( v123 )
  {
    v123 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
  }
  v107 = v122;
  if ( v122 )
  {
    v122 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
  }
  v108 = v121;
  if ( v121 )
  {
    v121 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v108 + 16LL))(v108);
  }
  v109 = v120;
  if ( v120 )
  {
    v120 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v109 + 16LL))(v109);
  }
  return 0;
}

```

## disassembly

```asm
0x14007de14  mov     [rsp-8+arg_10], rbx
0x14007de19  mov     [rsp-8+arg_18], rsi
0x14007de1e  push    rbp
0x14007de1f  push    rdi
0x14007de20  push    r12
0x14007de22  push    r14
0x14007de24  push    r15
0x14007de26  lea     rbp, [rsp-37h]
0x14007de2b  sub     rsp, 0E0h
0x14007de32  mov     rax, cs:__security_cookie
0x14007de39  xor     rax, rsp
0x14007de3c  mov     [rbp+57h+var_30], rax
0x14007de40  mov     r15, rdx
0x14007de43  mov     rdi, rcx
0x14007de46  xor     r12d, r12d
0x14007de49  mov     [rbp+57h+var_C0], r12
0x14007de4d  mov     [rbp+57h+string], r12
0x14007de51  lea     r9, [rbp+57h+string]; string
0x14007de55  lea     r8, [rbp+57h+var_74+4]; hstringHeader
0x14007de59  lea     edx, [r12+45h]; length
0x14007de5e  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x14007de65  call    cs:__imp_WindowsCreateStringReference
0x14007de6b  test    eax, eax
0x14007de6d  js      loc_14007EB1E
0x14007de73  mov     rbx, [rbp+57h+string]
0x14007de77  mov     rcx, [rbp+57h+var_C0]
0x14007de7b  test    rcx, rcx
0x14007de7e  jz      short loc_14007DE91
0x14007de80  mov     [rbp+57h+var_C0], r12
0x14007de84  mov     rax, [rcx]
0x14007de87  mov     rax, [rax+10h]
0x14007de8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007de90  nop
0x14007de91  lea     r8, [rbp+57h+var_C0]
0x14007de95  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x14007de9c  mov     rcx, rbx
0x14007de9f  call    cs:__imp_RoGetActivationFactory
0x14007dea5  mov     ebx, eax
0x14007dea7  test    eax, eax
0x14007dea9  jns     short loc_14007DEE3
0x14007deab  mov     rcx, [rbp+5Fh]; this
0x14007deaf  mov     r9d, eax; char *
0x14007deb2  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\corelib\\m"...
0x14007deb9  mov     edx, 16Ah; void *
0x14007debe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007dec3  nop
0x14007dec4  mov     rcx, [rbp+57h+var_C0]
0x14007dec8  test    rcx, rcx
0x14007decb  jz      short loc_14007DEDE
0x14007decd  mov     [rbp+57h+var_C0], r12
0x14007ded1  mov     rax, [rcx]
0x14007ded4  mov     rax, [rax+10h]
0x14007ded8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007dedd  nop
0x14007dede  jmp     loc_14007EAEC
0x14007dee3  mov     [rbp+57h+var_B8], r12
0x14007dee7  mov     rbx, [rbp+57h+var_C0]
0x14007deeb  mov     rsi, [rbx]
0x14007deee  mov     [rbp+57h+string], r12
0x14007def2  lea     r9, [rbp+57h+string]; string
0x14007def6  lea     r8, [rbp+57h+var_74+4]; hstringHeader
0x14007defa  mov     edx, 1Bh; length
0x14007deff  lea     rcx, aHttpsLoginWind; "https://login.windows.local"
0x14007df06  call    cs:__imp_WindowsCreateStringReference
0x14007df0c  test    eax, eax
0x14007df0e  js      loc_14007EB26
0x14007df14  lea     r8, [rbp+57h+var_B8]
0x14007df18  mov     rdx, [rbp+57h+string]
0x14007df1c  mov     rcx, rbx
0x14007df1f  mov     rax, [rsi+58h]
0x14007df23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007df28  mov     ebx, eax
0x14007df2a  test    eax, eax
0x14007df2c  jns     short loc_14007DF80
0x14007df2e  mov     rcx, [rbp+5Fh]; this
0x14007df32  mov     r9d, eax; char *
0x14007df35  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\corelib\\m"...
0x14007df3c  mov     edx, 16Eh; void *
0x14007df41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007df46  nop
0x14007df47  mov     rcx, [rbp+57h+var_B8]
0x14007df4b  test    rcx, rcx
0x14007df4e  jz      short loc_14007DF61
0x14007df50  mov     [rbp+57h+var_B8], r12
0x14007df54  mov     rax, [rcx]
0x14007df57  mov     rax, [rax+10h]
0x14007df5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007df60  nop
0x14007df61  mov     rcx, [rbp+57h+var_C0]
0x14007df65  test    rcx, rcx
0x14007df68  jz      short loc_14007DF7B
0x14007df6a  mov     [rbp+57h+var_C0], r12
0x14007df6e  mov     rax, [rcx]
0x14007df71  mov     rax, [rax+10h]
0x14007df75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007df7a  nop
0x14007df7b  jmp     loc_14007EAEC
0x14007df80  mov     [rbp+57h+var_B0], r12
0x14007df84  lea     rdx, [rbp+57h+var_B0]
0x14007df88  mov     rcx, [rbp+57h+var_B8]
0x14007df8c  call    ??$BlockOnCompletionAndGetResults@PEAVWebAccountProvider@Credentials@Security@Windows@@UIWebAccountProvider@234@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>>,tagCOWAIT_FLAGS,void *)
0x14007df91  mov     ebx, eax
0x14007df93  test    eax, eax
0x14007df95  jns     short loc_14007E003
0x14007df97  mov     rcx, [rbp+5Fh]; this
0x14007df9b  mov     r9d, eax; char *
0x14007df9e  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\corelib\\m"...
0x14007dfa5  mov     edx, 171h; void *
0x14007dfaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007dfaf  nop
0x14007dfb0  mov     rcx, [rbp+57h+var_B0]
0x14007dfb4  test    rcx, rcx
0x14007dfb7  jz      short loc_14007DFCA
0x14007dfb9  mov     [rbp+57h+var_B0], r12
0x14007dfbd  mov     rax, [rcx]
0x14007dfc0  mov     rax, [rax+10h]
0x14007dfc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007dfc9  nop
0x14007dfca  mov     rcx, [rbp+57h+var_B8]
0x14007dfce  test    rcx, rcx
0x14007dfd1  jz      short loc_14007DFE4
0x14007dfd3  mov     [rbp+57h+var_B8], r12
0x14007dfd7  mov     rax, [rcx]
0x14007dfda  mov     rax, [rax+10h]
0x14007dfde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007dfe3  nop
0x14007dfe4  mov     rcx, [rbp+57h+var_C0]
0x14007dfe8  test    rcx, rcx
0x14007dfeb  jz      short loc_14007DFFE
0x14007dfed  mov     [rbp+57h+var_C0], r12
0x14007dff1  mov     rax, [rcx]
0x14007dff4  mov     rax, [rax+10h]
0x14007dff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007dffd  nop
0x14007dffe  jmp     loc_14007EAEC
0x14007e003  cmp     [rbp+57h+var_B0], r12
0x14007e007  jnz     short loc_14007E07A
0x14007e009  mov     rcx, [rbp+5Fh]; this
0x14007e00d  mov     ebx, 80004003h
0x14007e012  mov     r9d, ebx; char *
0x14007e015  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\corelib\\m"...
0x14007e01c  mov     edx, 172h; void *
0x14007e021  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007e026  nop
0x14007e027  mov     rcx, [rbp+57h+var_B0]
0x14007e02b  test    rcx, rcx
0x14007e02e  jz      short loc_14007E041
0x14007e030  mov     [rbp+57h+var_B0], r12
0x14007e034  mov     rax, [rcx]
0x14007e037  mov     rax, [rax+10h]
0x14007e03b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e040  nop
0x14007e041  mov     rcx, [rbp+57h+var_B8]
0x14007e045  test    rcx, rcx
0x14007e048  jz      short loc_14007E05B
0x14007e04a  mov     [rbp+57h+var_B8], r12
0x14007e04e  mov     rax, [rcx]
0x14007e051  mov     rax, [rax+10h]
0x14007e055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e05a  nop
0x14007e05b  mov     rcx, [rbp+57h+var_C0]
0x14007e05f  test    rcx, rcx
0x14007e062  jz      short loc_14007E075
0x14007e064  mov     [rbp+57h+var_C0], r12
0x14007e068  mov     rdx, [rcx]
0x14007e06b  mov     rax, [rdx+10h]
0x14007e06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e074  nop
0x14007e075  jmp     loc_14007EAEC
0x14007e07a  mov     [rbp+57h+var_A8], r12
0x14007e07e  mov     [rbp+57h+string], r12
0x14007e082  lea     r9, [rbp+57h+string]; string
0x14007e086  lea     r8, [rbp+57h+var_74+4]; hstringHeader
0x14007e08a  mov     edx, 38h ; '8'; length
0x14007e08f  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x14007e096  call    cs:__imp_WindowsCreateStringReference
0x14007e09c  test    eax, eax
0x14007e09e  js      loc_14007EB16
0x14007e0a4  mov     rbx, [rbp+57h+string]
0x14007e0a8  mov     rcx, [rbp+57h+var_A8]
0x14007e0ac  test    rcx, rcx
0x14007e0af  jz      short loc_14007E0C2
0x14007e0b1  mov     [rbp+57h+var_A8], r12
0x14007e0b5  mov     rax, [rcx]
0x14007e0b8  mov     rax, [rax+10h]
0x14007e0bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e0c1  nop
0x14007e0c2  lea     r8, [rbp+57h+var_A8]
0x14007e0c6  lea     rdx, _GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9
0x14007e0cd  mov     rcx, rbx
0x14007e0d0  call    cs:__imp_RoGetActivationFactory
0x14007e0d6  mov     ebx, eax
0x14007e0d8  test    eax, eax
0x14007e0da  jns     loc_14007E166
0x14007e0e0  mov     rcx, [rbp+5Fh]; this
0x14007e0e4  mov     r9d, eax; char *
0x14007e0e7  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\corelib\\m"...
0x14007e0ee  mov     edx, 175h; void *
0x14007e0f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007e0f8  nop
0x14007e0f9  mov     rcx, [rbp+57h+var_A8]
0x14007e0fd  test    rcx, rcx
0x14007e100  jz      short loc_14007E113
0x14007e102  mov     [rbp+57h+var_A8], r12
0x14007e106  mov     rax, [rcx]
0x14007e109  mov     rax, [rax+10h]
0x14007e10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e112  nop
0x14007e113  mov     rcx, [rbp+57h+var_B0]
0x14007e117  test    rcx, rcx
0x14007e11a  jz      short loc_14007E12D
0x14007e11c  mov     [rbp+57h+var_B0], r12
0x14007e120  mov     rax, [rcx]
0x14007e123  mov     rax, [rax+10h]
0x14007e127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e12c  nop
0x14007e12d  mov     rcx, [rbp+57h+var_B8]
0x14007e131  test    rcx, rcx
0x14007e134  jz      short loc_14007E147
0x14007e136  mov     [rbp+57h+var_B8], r12
0x14007e13a  mov     rax, [rcx]
0x14007e13d  mov     rax, [rax+10h]
0x14007e141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e146  nop
0x14007e147  mov     rcx, [rbp+57h+var_C0]
0x14007e14b  test    rcx, rcx
0x14007e14e  jz      short loc_14007E161
0x14007e150  mov     [rbp+57h+var_C0], r12
0x14007e154  mov     rax, [rcx]
0x14007e157  mov     rax, [rax+10h]
0x14007e15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e160  nop
0x14007e161  jmp     loc_14007EAEC
0x14007e166  mov     [rbp+57h+var_A0], r12
0x14007e16a  mov     rbx, [rbp+57h+var_A8]
0x14007e16e  mov     rax, [rbx]
0x14007e171  mov     r14, [rax+38h]
0x14007e175  lea     rdx, off_1400B0B00; "{f1273a19-b987-46a7-8564-c35a5e715902}"
0x14007e17c  lea     rcx, [rbp+57h+var_74+4]
0x14007e180  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14007e185  nop
0x14007e186  mov     rsi, [rax+18h]
0x14007e18a  cmp     qword ptr [rdi+18h], 7
0x14007e18f  jbe     short loc_14007E194
0x14007e191  mov     rdi, [rdi]
0x14007e194  mov     [rbp+57h+var_80], rdi
0x14007e198  lea     rdx, [rbp+57h+var_80]
0x14007e19c  lea     rcx, [rbp+57h+var_50]
0x14007e1a0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14007e1a5  nop
0x14007e1a6  lea     rcx, [rbp+57h+var_A0]
0x14007e1aa  mov     [rsp+100h+var_D8], rcx
0x14007e1af  mov     [rsp+100h+var_E0], 1; int
0x14007e1b7  mov     r9, rsi
0x14007e1ba  mov     r8, [rax+18h]
0x14007e1be  mov     rdx, [rbp+57h+var_B0]
0x14007e1c2  mov     rcx, rbx
0x14007e1c5  mov     rax, r14
0x14007e1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e1cd  mov     ebx, eax
0x14007e1cf  test    eax, eax
0x14007e1d1  jns     loc_14007E277
0x14007e1d7  mov     rcx, [rbp+5Fh]; this
0x14007e1db  mov     r9d, eax; char *
0x14007e1de  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\corelib\\m"...
0x14007e1e5  mov     edx, 17Ch; void *
0x14007e1ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007e1ef  nop
0x14007e1f0  mov     rcx, [rbp+57h+var_A0]
0x14007e1f4  test    rcx, rcx
0x14007e1f7  jz      short loc_14007E20A
0x14007e1f9  mov     [rbp+57h+var_A0], r12
0x14007e1fd  mov     rax, [rcx]
0x14007e200  mov     rax, [rax+10h]
0x14007e204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e209  nop
0x14007e20a  mov     rcx, [rbp+57h+var_A8]
0x14007e20e  test    rcx, rcx
0x14007e211  jz      short loc_14007E224
0x14007e213  mov     [rbp+57h+var_A8], r12
0x14007e217  mov     rax, [rcx]
0x14007e21a  mov     rax, [rax+10h]
0x14007e21e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e223  nop
0x14007e224  mov     rcx, [rbp+57h+var_B0]
0x14007e228  test    rcx, rcx
0x14007e22b  jz      short loc_14007E23E
0x14007e22d  mov     [rbp+57h+var_B0], r12
0x14007e231  mov     rax, [rcx]
0x14007e234  mov     rax, [rax+10h]
0x14007e238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e23d  nop
0x14007e23e  mov     rcx, [rbp+57h+var_B8]
0x14007e242  test    rcx, rcx
0x14007e245  jz      short loc_14007E258
0x14007e247  mov     [rbp+57h+var_B8], r12
0x14007e24b  mov     rax, [rcx]
0x14007e24e  mov     rax, [rax+10h]
0x14007e252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e257  nop
  ... truncated ...
```
