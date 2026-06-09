# AADUtil::GetAADDeviceTicketAndDataBoundary(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *,wchar_t * *)

- ea: `0x1801f578c`
- end: `0x1801f6034`
- name: `?GetAADDeviceTicketAndDataBoundary@AADUtil@@YAJPEB_W000PEAPEA_W1@Z`
- size: `2216`
- prototype: `__int64 __fastcall(AADUtil *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, wchar_t **, wchar_t **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801b6e5c`

## callees

- `0x18000def4`
- `0x18007b8a4`
- `0x18007e2f8`
- `0x1800b30b8`
- `0x1801aaab4`
- `0x1801f53b0`
- `0x1801f578c`
- `0x1801f603c`
- `0x1801f6314`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801f58c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801f5a27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801f5c11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801f5ca4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801f5d27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801f5d55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801f58c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801f5a27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801f5c11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801f5ca4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801f5d27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801f5d55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5cec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5cfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5e1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5ec8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5ed6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5fce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5fdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5cec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5cfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5e1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5ec8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5ed6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5fce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5fdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f5e92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f5e92`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801f5901`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801f5a62`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801f5901`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801f5a62`

## string_xrefs

- `0x1801f5a20`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`
- `0x1801f58bf`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x1801f5d4e`: `client_TokenType`

## pseudocode

```c
// Hidden C++ exception states: #wind=148
__int64 __fastcall AADUtil::GetAADDeviceTicketAndDataBoundary(
        const OLECHAR *this,
        wchar_t *a2,
        wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        wchar_t **a6)
{
  int v9; // ebx
  __int64 v10; // rdx
  HRESULT v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  HSTRING v14; // rbx
  void (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rcx
  int ActivationFactory; // eax
  void (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rbx
  void (__fastcall *v18)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 *); // rdi
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rdi
  HRESULT v25; // eax
  int v26; // edx
  unsigned int v27; // r8d
  HSTRING v28; // rbx
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rbx
  __int64 (__fastcall *v32)(__int64, __int64, _QWORD, HSTRING); // rsi
  HSTRING v33; // rdi
  __int64 v34; // rax
  int v35; // eax
  int v36; // eax
  __int64 v37; // rdx
  HSTRING v38; // rbx
  __int64 (__fastcall *v39)(HSTRING, _QWORD); // rdi
  __int64 v40; // rax
  HSTRING v41; // rcx
  HSTRING v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rbx
  __int64 (__fastcall *v45)(__int64, HSTRING, HSTRING, _BYTE *); // rsi
  HSTRING v46; // rdi
  HRESULT v47; // eax
  int v48; // edx
  unsigned int v49; // r8d
  unsigned __int64 v50; // r9
  int v51; // eax
  __int64 v52; // rdx
  __int64 v53; // rbx
  __int64 (__fastcall *v54)(__int64, HSTRING, HSTRING, _BYTE *); // rsi
  HSTRING v55; // rdi
  HRESULT v56; // eax
  int v57; // edx
  unsigned int v58; // r8d
  __int64 v59; // rbx
  __int64 (__fastcall *v60)(__int64, HSTRING, HSTRING, _BYTE *); // rsi
  HRESULT v61; // eax
  int v62; // edx
  unsigned int v63; // r8d
  HSTRING v64; // rdi
  HRESULT v65; // eax
  int v66; // edx
  unsigned int v67; // r8d
  int v68; // eax
  __int64 v69; // rdx
  __int64 v70; // rdi
  HSTRING v71; // rcx
  __int64 v72; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v74; // rcx
  HSTRING v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  void (__fastcall ***v82)(_QWORD, _QWORD, _QWORD); // rcx
  int v84; // [rsp+20h] [rbp-E0h]
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING_HEADER v87; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v88; // [rsp+78h] [rbp-88h] BYREF
  HSTRING v89; // [rsp+80h] [rbp-80h] BYREF
  const OLECHAR *v90; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *v91; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v92; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v93[8]; // [rsp+A0h] [rbp-60h] BYREF
  void (__fastcall ***v94)(_QWORD, GUID *, __int64 *); // [rsp+A8h] [rbp-58h] BYREF
  __int64 v95; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v96; // [rsp+B8h] [rbp-48h]
  __int64 v97; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v98; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING v99; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING v100; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v101; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v102; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v103; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v104; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING v105; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v106; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v90 = this;
  v89 = (HSTRING)a2;
  v91 = a3;
  v92 = a4;
  if ( a6 )
  {
    *a6 = 0;
    v105 = 0;
    v100 = 0;
    if ( a2 && *a2 )
    {
      v9 = Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(&v105);
      if ( v9 < 0 )
      {
        v10 = 173;
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
          (const char *)(unsigned int)v9,
          v84);
LABEL_103:
        WindowsDeleteString(v100);
        v100 = 0;
        WindowsDeleteString(v105);
        return (unsigned int)v9;
      }
    }
    else
    {
      v9 = Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(&v105);
      if ( v9 < 0 )
      {
        v10 = 178;
        goto LABEL_15;
      }
    }
    if ( this && *this )
    {
      v9 = Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(&v100);
      if ( v9 < 0 )
      {
        v10 = 183;
        goto LABEL_15;
      }
    }
    else
    {
      v9 = Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(&v100);
      if ( v9 < 0 )
      {
        v10 = 188;
        goto LABEL_15;
      }
    }
    v94 = 0;
    v98 = 0;
    string = 0;
    v11 = WindowsCreateStringReference(
            L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
            0x45u,
            &hstringHeader,
            &string);
    if ( v11 >= 0 )
    {
      v14 = string;
      v15 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v94;
      if ( v94 )
      {
        v94 = 0;
        ((void (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v15)[2])(v15);
      }
      ActivationFactory = RoGetActivationFactory(v14, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v94);
      v9 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC4,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
          (const char *)(unsigned int)ActivationFactory,
          v84);
LABEL_99:
        v81 = v98;
        if ( v98 )
        {
          v98 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
        }
        v82 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v94;
        if ( v94 )
        {
          v94 = 0;
          ((void (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v82)[2])(v82);
        }
        goto LABEL_103;
      }
      v17 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v94;
      v18 = **v94;
      v19 = v98;
      if ( v98 )
      {
        v98 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      v18(v17, &GUID_54e633fe_96e0_41e8_9832_1298897c2aaf, &v98);
      v104 = 0;
      v20 = v98;
      v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v98 + 64LL);
      v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v87, off_1802E96F8);
      v23 = v21(v20, *(_QWORD *)(v22 + 24), &v104);
      v9 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
          (const char *)(unsigned int)v23,
          v84);
LABEL_97:
        v80 = v104;
        if ( v104 )
        {
          v104 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
        }
        goto LABEL_99;
      }
      v103 = 0;
      v24 = v104;
      v9 = wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *>(v104);
      if ( v9 >= 0 )
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 64LL))(v24, &v103);
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCC,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
          (const char *)(unsigned int)v9,
          v84);
LABEL_95:
        v79 = v103;
        if ( v103 )
        {
          v103 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
        }
        goto LABEL_97;
      }
      v97 = 0;
      string = 0;
      v25 = WindowsCreateStringReference(
              L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
              0x38u,
              &hstringHeader,
              &string);
      if ( v25 < 0 )
        goto LABEL_107;
      v28 = string;
      v29 = v97;
      if ( v97 )
      {
        v97 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      v30 = RoGetActivationFactory(v28, &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9, &v97);
      v9 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD1,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
          (const char *)(unsigned int)v30,
          v84);
LABEL_93:
        v78 = v97;
        if ( v97 )
        {
          v97 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        }
        goto LABEL_95;
      }
      v90 = &OutputString;
      v96 = 0;
      v31 = v97;
      v32 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, HSTRING))(*(_QWORD *)v97 + 56LL);
      v33 = v105;
      v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v87, &v90);
      v35 = v32(v31, v103, *(_QWORD *)(v34 + 24), v33);
      v9 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDB,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
          (const char *)(unsigned int)v35,
          0);
LABEL_91:
        v77 = v96;
        if ( v96 )
        {
          v96 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
        }
        goto LABEL_93;
      }
      if ( a4 && *a4 )
      {
        v89 = 0;
        v36 = (**(__int64 (__fastcall ***)(__int64, GUID *, HSTRING *))v96)(
                v96,
                &GUID_5a755b51_3bb1_41a5_a63d_90bc32c7db9a,
                &v89);
        v9 = v36;
        if ( v36 < 0 )
        {
          v37 = 225;
          goto LABEL_42;
        }
        v38 = v89;
        v39 = *(__int64 (__fastcall **)(HSTRING, _QWORD))(*(_QWORD *)v89 + 56LL);
        v40 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v87, &v92);
        v36 = v39(v38, *(_QWORD *)(v40 + 24));
        v9 = v36;
        if ( v36 < 0 )
        {
          v37 = 226;
LABEL_42:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v37,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
            (const char *)(unsigned int)v36,
            0);
          v41 = v89;
          if ( v89 )
          {
            v89 = 0;
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v41 + 16LL))(v41);
          }
          goto LABEL_91;
        }
        v42 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v42 + 16LL))(v42);
        }
      }
      v95 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v96 + 80LL))(v96, &v95);
      if ( v9 < 0 )
      {
        v43 = 230;
LABEL_52:
        v50 = (unsigned int)v9;
LABEL_66:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v43,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
          (const char *)v50,
          0);
LABEL_89:
        v76 = v95;
        if ( v95 )
        {
          v95 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        }
        goto LABEL_91;
      }
      v93[0] = 0;
      v44 = v95;
      v45 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _BYTE *))(*(_QWORD *)v95 + 80LL);
      v46 = v100;
      string = 0;
      v47 = WindowsCreateStringReference(L"resource", 8u, &hstringHeader, &string);
      if ( v47 < 0 )
        goto LABEL_108;
      v9 = v45(v44, string, v46, v93);
      if ( v9 < 0 )
      {
        v43 = 235;
        goto LABEL_52;
      }
      if ( a3 && *a3 )
      {
        v89 = 0;
        v51 = Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(&v89);
        v9 = v51;
        if ( v51 < 0 )
        {
          v52 = 241;
LABEL_60:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v52,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
            (const char *)(unsigned int)v51,
            0);
          WindowsDeleteString(v89);
          goto LABEL_89;
        }
        v53 = v95;
        v54 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _BYTE *))(*(_QWORD *)v95 + 80LL);
        v55 = v89;
        string = 0;
        v56 = WindowsCreateStringReference(L"authority", 9u, &hstringHeader, &string);
        if ( v56 < 0 )
          goto LABEL_109;
        v51 = v54(v53, string, v55, v93);
        v9 = v51;
        if ( v51 < 0 )
        {
          v52 = 243;
          goto LABEL_60;
        }
        WindowsDeleteString(v89);
      }
      v59 = v95;
      v60 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _BYTE *))(*(_QWORD *)v95 + 80LL);
      string = 0;
      v61 = WindowsCreateStringReference(L"DeviceAuth", 0xAu, &hstringHeader, &string);
      if ( v61 < 0 )
      {
LABEL_110:
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v61, v62, v63);
        JUMPOUT(0x1801F6033LL);
      }
      v64 = string;
      v88 = 0;
      v65 = WindowsCreateStringReference(L"client_TokenType", 0x10u, &v87, &v88);
      if ( v65 >= 0 )
      {
        v68 = v60(v59, v88, v64, v93);
        v9 = v68;
        if ( v68 < 0 )
        {
          v50 = (unsigned int)v68;
          v43 = 248;
          goto LABEL_66;
        }
        v102 = 0;
        v101 = 0;
        v9 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64 *))(*v94)[6])(v94, v96, &v101);
        if ( v9 < 0 )
        {
          v69 = 252;
LABEL_73:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v69,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
            (const char *)(unsigned int)v9,
            0);
LABEL_85:
          v74 = v101;
          if ( v101 )
          {
            v101 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
          }
          v75 = v102;
          if ( v102 )
          {
            v102 = 0;
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v75 + 16LL))(v75);
          }
          goto LABEL_89;
        }
        v70 = v101;
        v9 = wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(v101);
        if ( v9 >= 0 )
          v9 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v70 + 64LL))(v70, &v102);
        if ( v9 < 0 )
        {
          v69 = 254;
          goto LABEL_73;
        }
        v106 = 0;
        v99 = 0;
        WindowsDeleteString(0);
        v99 = 0;
        v89 = v102;
        if ( v102 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v102 + 8LL))(v102);
        v9 = AADUtil::ExtractAADDeviceTicketAndDataBoundary(&v89, 0, &v99);
        v71 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v71 + 16LL))(v71);
        }
        if ( v9 >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(v99, 0);
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
            &v91,
            StringRawBuffer,
            -1);
          if ( v91 )
          {
            *a6 = v91;
            v9 = 0;
            goto LABEL_84;
          }
          v9 = -2147024882;
          v72 = 273;
        }
        else
        {
          v72 = 260;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v72,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
          (const char *)(unsigned int)v9,
          0);
LABEL_84:
        WindowsDeleteString(v99);
        v99 = 0;
        WindowsDeleteString(v106);
        v106 = 0;
        goto LABEL_85;
      }
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v65, v66, v67);
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
LABEL_107:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v25, v26, v27);
LABEL_108:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v47, v48, v49);
LABEL_109:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v56, v57, v58);
    goto LABEL_110;
  }
  v9 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9B,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
    (const char *)0x80004003LL,
    v84);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1801f578c  push    rbp
0x1801f578e  push    rbx
0x1801f578f  push    rsi
0x1801f5790  push    rdi
0x1801f5791  push    r12
0x1801f5793  push    r13
0x1801f5795  push    r14
0x1801f5797  push    r15
0x1801f5799  lea     rbp, [rsp-28h]
0x1801f579e  sub     rsp, 128h
0x1801f57a5  mov     rax, cs:__security_cookie
0x1801f57ac  xor     rax, rsp
0x1801f57af  mov     [rbp+60h+var_50], rax
0x1801f57b3  mov     r14, r9
0x1801f57b6  mov     r15, r8
0x1801f57b9  mov     rdi, rcx
0x1801f57bc  mov     [rbp+60h+var_D8], rcx
0x1801f57c0  mov     [rbp+60h+var_E0], rdx
0x1801f57c4  mov     [rbp+60h+var_D0], r8
0x1801f57c8  mov     [rbp+60h+var_C8], r9
0x1801f57cc  mov     r12, [rbp+60h+arg_28]
0x1801f57d3  xor     r13d, r13d
0x1801f57d6  test    r12, r12
0x1801f57d9  jnz     short loc_1801F57FD
0x1801f57db  mov     rcx, [rbp+68h]; this
0x1801f57df  mov     ebx, 80004003h
0x1801f57e4  mov     r9d, ebx; char *
0x1801f57e7  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1801f57ee  mov     edx, 9Bh; void *
0x1801f57f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f57f8  jmp     loc_1801F5FE2
0x1801f57fd  mov     [r12], r13
0x1801f5801  mov     [rbp+60h+var_60], r13
0x1801f5805  mov     [rbp+60h+var_88], r13
0x1801f5809  test    rdx, rdx
0x1801f580c  jz      short loc_1801F582E
0x1801f580e  cmp     [rdx], r13w
0x1801f5812  jz      short loc_1801F582E
0x1801f5814  lea     rdx, [rbp+60h+var_E0]
0x1801f5818  lea     rcx, [rbp+60h+var_60]; string
0x1801f581c  call    ??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1801f5821  mov     ebx, eax
0x1801f5823  test    eax, eax
0x1801f5825  jns     short loc_1801F584B
0x1801f5827  mov     edx, 0ADh
0x1801f582c  jmp     short loc_1801F588B
0x1801f582e  lea     rdx, off_1802E9708; "d1580516-bbf9-47df-9eda-207f2540e83d"
0x1801f5835  lea     rcx, [rbp+60h+var_60]; string
0x1801f5839  call    ??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1801f583e  mov     ebx, eax
0x1801f5840  test    eax, eax
0x1801f5842  jns     short loc_1801F584B
0x1801f5844  mov     edx, 0B2h
0x1801f5849  jmp     short loc_1801F588B
0x1801f584b  test    rdi, rdi
0x1801f584e  jz      short loc_1801F5870
0x1801f5850  cmp     [rdi], r13w
0x1801f5854  jz      short loc_1801F5870
0x1801f5856  lea     rdx, [rbp+60h+var_D8]
0x1801f585a  lea     rcx, [rbp+60h+var_88]; string
0x1801f585e  call    ??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1801f5863  mov     ebx, eax
0x1801f5865  test    eax, eax
0x1801f5867  jns     short loc_1801F58A3
0x1801f5869  mov     edx, 0B7h
0x1801f586e  jmp     short loc_1801F588B
0x1801f5870  lea     rdx, off_1802E96F0; "https://login.windows.local"
0x1801f5877  lea     rcx, [rbp+60h+var_88]; string
0x1801f587b  call    ??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1801f5880  mov     ebx, eax
0x1801f5882  test    eax, eax
0x1801f5884  jns     short loc_1801F58A3
0x1801f5886  mov     edx, 0BCh; void *
0x1801f588b  mov     rcx, [rbp+68h]; this
0x1801f588f  mov     r9d, ebx; char *
0x1801f5892  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1801f5899  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f589e  jmp     loc_1801F5FCA
0x1801f58a3  mov     [rbp+60h+var_B8], r13
0x1801f58a7  mov     [rbp+60h+var_98], r13
0x1801f58ab  mov     [rsp+160h+string], r13
0x1801f58b0  lea     r9, [rsp+160h+string]; string
0x1801f58b5  lea     r8, [rsp+160h+hstringHeader]; hstringHeader
0x1801f58ba  mov     edx, 45h ; 'E'; length
0x1801f58bf  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QB_WB; "Windows.Security.Authentication.Web.Cor"...
0x1801f58c6  call    cs:__imp_WindowsCreateStringReference
0x1801f58cc  test    eax, eax
0x1801f58ce  js      loc_1801F600C
0x1801f58d4  mov     rbx, [rsp+160h+string]
0x1801f58d9  mov     rcx, [rbp+60h+var_B8]
0x1801f58dd  test    rcx, rcx
0x1801f58e0  jz      short loc_1801F58F3
0x1801f58e2  mov     [rbp+60h+var_B8], r13
0x1801f58e6  mov     rax, [rcx]
0x1801f58e9  mov     rax, [rax+10h]
0x1801f58ed  call    _guard_dispatch_icall
0x1801f58f2  nop
0x1801f58f3  lea     r8, [rbp+60h+var_B8]
0x1801f58f7  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x1801f58fe  mov     rcx, rbx
0x1801f5901  call    cs:__imp_RoGetActivationFactory
0x1801f5907  mov     ebx, eax
0x1801f5909  test    eax, eax
0x1801f590b  jns     short loc_1801F592A
0x1801f590d  mov     rcx, [rbp+68h]; this
0x1801f5911  mov     r9d, eax; char *
0x1801f5914  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1801f591b  mov     edx, 0C4h; void *
0x1801f5920  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f5925  jmp     loc_1801F5F96
0x1801f592a  mov     rbx, [rbp+60h+var_B8]
0x1801f592e  mov     rax, [rbx]
0x1801f5931  mov     rdi, [rax]
0x1801f5934  mov     rcx, [rbp+60h+var_98]
0x1801f5938  test    rcx, rcx
0x1801f593b  jz      short loc_1801F594E
0x1801f593d  mov     [rbp+60h+var_98], r13
0x1801f5941  mov     rdx, [rcx]
0x1801f5944  mov     rax, [rdx+10h]
0x1801f5948  call    _guard_dispatch_icall
0x1801f594d  nop
0x1801f594e  lea     r8, [rbp+60h+var_98]
0x1801f5952  lea     rdx, _GUID_54e633fe_96e0_41e8_9832_1298897c2aaf
0x1801f5959  mov     rcx, rbx
0x1801f595c  mov     rax, rdi
0x1801f595f  call    _guard_dispatch_icall
0x1801f5964  nop
0x1801f5965  mov     [rbp+60h+var_68], r13
0x1801f5969  mov     rbx, [rbp+60h+var_98]
0x1801f596d  mov     rax, [rbx]
0x1801f5970  mov     rdi, [rax+40h]
0x1801f5974  lea     rdx, off_1802E96F8; "https://login.windows.net"
0x1801f597b  lea     rcx, [rsp+160h+var_100]
0x1801f5980  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x1801f5985  nop
0x1801f5986  lea     r8, [rbp+60h+var_68]
0x1801f598a  mov     rdx, [rax+18h]
0x1801f598e  mov     rcx, rbx
0x1801f5991  mov     rax, rdi
0x1801f5994  call    _guard_dispatch_icall
0x1801f5999  mov     ebx, eax
0x1801f599b  test    eax, eax
0x1801f599d  jns     short loc_1801F59BC
0x1801f599f  mov     rcx, [rbp+68h]; this
0x1801f59a3  mov     r9d, eax; char *
0x1801f59a6  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1801f59ad  mov     edx, 0C9h; void *
0x1801f59b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f59b7  jmp     loc_1801F5F7C
0x1801f59bc  mov     [rbp+60h+var_70], r13
0x1801f59c0  mov     rdi, [rbp+60h+var_68]
0x1801f59c4  mov     rcx, rdi
0x1801f59c7  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x1801f59cc  mov     ebx, eax
0x1801f59ce  test    eax, eax
0x1801f59d0  js      short loc_1801F59E7
0x1801f59d2  mov     rax, [rdi]
0x1801f59d5  lea     rdx, [rbp+60h+var_70]
0x1801f59d9  mov     rcx, rdi
0x1801f59dc  mov     rax, [rax+40h]
0x1801f59e0  call    _guard_dispatch_icall
0x1801f59e5  mov     ebx, eax
0x1801f59e7  test    ebx, ebx
0x1801f59e9  jns     short loc_1801F5A08
0x1801f59eb  mov     rcx, [rbp+68h]; this
0x1801f59ef  mov     r9d, ebx; char *
0x1801f59f2  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1801f59f9  mov     edx, 0CCh; void *
0x1801f59fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f5a03  jmp     loc_1801F5F62
0x1801f5a08  mov     [rbp+60h+var_A0], r13
0x1801f5a0c  mov     [rsp+160h+string], r13
0x1801f5a11  lea     r9, [rsp+160h+string]; string
0x1801f5a16  lea     r8, [rsp+160h+hstringHeader]; hstringHeader
0x1801f5a1b  mov     edx, 38h ; '8'; length
0x1801f5a20  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QB_WB; "Windows.Security.Authentication.Web.Cor"...
0x1801f5a27  call    cs:__imp_WindowsCreateStringReference
0x1801f5a2d  test    eax, eax
0x1801f5a2f  js      loc_1801F6014
0x1801f5a35  mov     rbx, [rsp+160h+string]
0x1801f5a3a  mov     rcx, [rbp+60h+var_A0]
0x1801f5a3e  test    rcx, rcx
0x1801f5a41  jz      short loc_1801F5A54
0x1801f5a43  mov     [rbp+60h+var_A0], r13
0x1801f5a47  mov     rax, [rcx]
0x1801f5a4a  mov     rax, [rax+10h]
0x1801f5a4e  call    _guard_dispatch_icall
0x1801f5a53  nop
0x1801f5a54  lea     r8, [rbp+60h+var_A0]
0x1801f5a58  lea     rdx, _GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9
0x1801f5a5f  mov     rcx, rbx
0x1801f5a62  call    cs:__imp_RoGetActivationFactory
0x1801f5a68  mov     ebx, eax
0x1801f5a6a  test    eax, eax
0x1801f5a6c  jns     short loc_1801F5A8B
0x1801f5a6e  mov     rcx, [rbp+68h]; this
0x1801f5a72  mov     r9d, eax; char *
0x1801f5a75  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1801f5a7c  mov     edx, 0D1h; void *
0x1801f5a81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f5a86  jmp     loc_1801F5F48
0x1801f5a8b  lea     rax, OutputString
0x1801f5a92  mov     [rbp+60h+var_D8], rax
0x1801f5a96  mov     [rbp+60h+var_A8], r13
0x1801f5a9a  mov     rbx, [rbp+60h+var_A0]
0x1801f5a9e  mov     rax, [rbx]
0x1801f5aa1  mov     rsi, [rax+38h]
0x1801f5aa5  mov     rdi, [rbp+60h+var_60]
0x1801f5aa9  lea     rdx, [rbp+60h+var_D8]
0x1801f5aad  lea     rcx, [rsp+160h+var_100]
0x1801f5ab2  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x1801f5ab7  nop
0x1801f5ab8  lea     rcx, [rbp+60h+var_A8]
0x1801f5abc  mov     [rsp+160h+var_138], rcx
0x1801f5ac1  mov     [rsp+160h+var_140], r13d; int
0x1801f5ac6  mov     r9, rdi
0x1801f5ac9  mov     r8, [rax+18h]
0x1801f5acd  mov     rdx, [rbp+60h+var_70]
0x1801f5ad1  mov     rcx, rbx
0x1801f5ad4  mov     rax, rsi
0x1801f5ad7  call    _guard_dispatch_icall
0x1801f5adc  mov     ebx, eax
0x1801f5ade  test    eax, eax
0x1801f5ae0  jns     short loc_1801F5AFF
0x1801f5ae2  mov     rcx, [rbp+68h]; this
0x1801f5ae6  mov     r9d, eax; char *
0x1801f5ae9  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1801f5af0  mov     edx, 0DBh; void *
0x1801f5af5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f5afa  jmp     loc_1801F5F2E
0x1801f5aff  test    r14, r14
0x1801f5b02  jz      loc_1801F5BBE
0x1801f5b08  cmp     [r14], r13w
0x1801f5b0c  jz      loc_1801F5BBE
0x1801f5b12  mov     [rbp+60h+var_E0], r13
0x1801f5b16  mov     rcx, [rbp+60h+var_A8]
0x1801f5b1a  mov     rax, [rcx]
0x1801f5b1d  lea     r8, [rbp+60h+var_E0]
0x1801f5b21  lea     rdx, _GUID_5a755b51_3bb1_41a5_a63d_90bc32c7db9a
0x1801f5b28  mov     rax, [rax]
0x1801f5b2b  call    _guard_dispatch_icall
0x1801f5b30  mov     ebx, eax
0x1801f5b32  test    eax, eax
0x1801f5b34  jns     short loc_1801F5B3D
0x1801f5b36  mov     edx, 0E1h
0x1801f5b3b  jmp     short loc_1801F5B71
0x1801f5b3d  mov     rbx, [rbp+60h+var_E0]
0x1801f5b41  mov     rax, [rbx]
0x1801f5b44  mov     rdi, [rax+38h]
0x1801f5b48  lea     rdx, [rbp+60h+var_C8]
0x1801f5b4c  lea     rcx, [rsp+160h+var_100]
0x1801f5b51  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x1801f5b56  nop
0x1801f5b57  mov     rdx, [rax+18h]
0x1801f5b5b  mov     rcx, rbx
0x1801f5b5e  mov     rax, rdi
0x1801f5b61  call    _guard_dispatch_icall
0x1801f5b66  mov     ebx, eax
0x1801f5b68  test    eax, eax
0x1801f5b6a  jns     short loc_1801F5BA4
0x1801f5b6c  mov     edx, 0E2h; void *
0x1801f5b71  mov     r9d, eax; char *
0x1801f5b74  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1801f5b7b  mov     rcx, [rbp+68h]; this
0x1801f5b7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f5b84  nop
0x1801f5b85  mov     rcx, [rbp+60h+var_E0]
0x1801f5b89  test    rcx, rcx
0x1801f5b8c  jz      short loc_1801F5B9F
0x1801f5b8e  mov     [rbp+60h+var_E0], r13
0x1801f5b92  mov     rax, [rcx]
0x1801f5b95  mov     rax, [rax+10h]
0x1801f5b99  call    _guard_dispatch_icall
0x1801f5b9e  nop
0x1801f5b9f  jmp     loc_1801F5F2E
0x1801f5ba4  mov     rcx, [rbp+60h+var_E0]
0x1801f5ba8  test    rcx, rcx
0x1801f5bab  jz      short loc_1801F5BBE
0x1801f5bad  mov     [rbp+60h+var_E0], r13
0x1801f5bb1  mov     rax, [rcx]
0x1801f5bb4  mov     rax, [rax+10h]
0x1801f5bb8  call    _guard_dispatch_icall
0x1801f5bbd  nop
0x1801f5bbe  mov     [rbp+60h+var_B0], r13
0x1801f5bc2  mov     rcx, [rbp+60h+var_A8]
0x1801f5bc6  mov     rax, [rcx]
0x1801f5bc9  lea     rdx, [rbp+60h+var_B0]
0x1801f5bcd  mov     rax, [rax+50h]
0x1801f5bd1  call    _guard_dispatch_icall
0x1801f5bd6  mov     ebx, eax
0x1801f5bd8  test    eax, eax
0x1801f5bda  jns     short loc_1801F5BE3
0x1801f5bdc  mov     edx, 0E6h
0x1801f5be1  jmp     short loc_1801F5C41
0x1801f5be3  mov     [rbp+60h+var_C0], r13b
0x1801f5be7  mov     rbx, [rbp+60h+var_B0]
0x1801f5beb  mov     rax, [rbx]
0x1801f5bee  mov     rsi, [rax+50h]
0x1801f5bf2  mov     rdi, [rbp+60h+var_88]
0x1801f5bf6  mov     [rsp+160h+string], r13
  ... truncated ...
```
