# CWUTelemetryScanFailedEvent::CreateFailedUpdateInfoJSON(_GUID const *,ulong,wchar_t * *)

- ea: `0x180162704`
- end: `0x180162efb`
- name: `?CreateFailedUpdateInfoJSON@CWUTelemetryScanFailedEvent@@IEAAJPEBU_GUID@@KPEAPEA_W@Z`
- size: `2039`
- prototype: `int(CWUTelemetryScanFailedEvent *__hidden this, const struct _GUID *, unsigned int, wchar_t **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801630b0`

## callees

- `0x18000def4`
- `0x18007b8a4`
- `0x1800b30b8`
- `0x180110914`
- `0x18011fff0`
- `0x18014ff34`
- `0x180162704`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180162969`
- `OLEAUT32!__imp_SysStringLen` at `0x180162bec`
- `OLEAUT32!__imp_SysStringLen` at `0x180162969`
- `OLEAUT32!__imp_SysStringLen` at `0x180162bec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18016275c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18016279f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180162866`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18016290c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801629f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180162ac1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180162b8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180162c73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180162d38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18016275c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18016279f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180162866`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18016290c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801629f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180162ac1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180162b8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180162c73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180162d38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180162dd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180162e3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180162dd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180162e3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180162e04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180162e04`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801627d9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801627d9`

## string_xrefs

- `0x180162755`: `Windows.Data.Json.JsonObject`
- `0x180162798`: `Windows.Data.Json.JsonValue`
- `0x180162905`: `FailedUpdateGuids`
- `0x180162aba`: `MSIError`
- `0x18016285f`: `FailedUpdatesCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=64
__int64 __fastcall CWUTelemetryScanFailedEvent::CreateFailedUpdateInfoJSON(
        CWUTelemetryScanFailedEvent *this,
        struct _GUID *a2,
        unsigned int a3,
        wchar_t **a4)
{
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  int ActivationFactory; // ebx
  __int64 v12; // rdx
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  HSTRING v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, __int64, unsigned int *); // rsi
  unsigned int *v21; // rcx
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v23)(_QWORD, GUID *, unsigned int *); // r15
  unsigned int *v24; // rsi
  HRESULT v25; // eax
  int v26; // edx
  unsigned int v27; // r8d
  __int64 v28; // rdx
  struct ABI::Windows::Data::Json::IJsonValue **v29; // r9
  unsigned int *v30; // rcx
  unsigned int *v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v33)(_QWORD, GUID *, unsigned int *); // r14
  unsigned int *v34; // rsi
  HRESULT v35; // eax
  int v36; // edx
  unsigned int v37; // r8d
  unsigned int *v38; // rcx
  OLECHAR *v39; // rcx
  __int64 v40; // rbx
  __int64 (__fastcall *v41)(__int64, _QWORD, unsigned int *); // r14
  unsigned int *v42; // rcx
  __int64 v43; // rax
  __int64 (__fastcall ***v44)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v45)(_QWORD, GUID *, unsigned int *); // r14
  unsigned int *v46; // rsi
  HRESULT v47; // eax
  int v48; // edx
  unsigned int v49; // r8d
  unsigned int *v50; // rcx
  __int64 v51; // rbx
  __int64 (__fastcall *v52)(__int64, __int64, unsigned int *); // rsi
  unsigned int *v53; // rcx
  __int64 (__fastcall ***v54)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v55)(_QWORD, GUID *, unsigned int *); // r14
  unsigned int *v56; // rsi
  HRESULT v57; // eax
  int v58; // edx
  unsigned int v59; // r8d
  unsigned int *v60; // rcx
  __int64 v61; // rbx
  __int64 (__fastcall *v62)(__int64, __int64, unsigned int *); // rsi
  unsigned int *v63; // rcx
  __int64 (__fastcall ***v64)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v65)(_QWORD, GUID *, unsigned int *); // r14
  unsigned int *v66; // rsi
  HRESULT v67; // eax
  int v68; // edx
  unsigned int v69; // r8d
  unsigned int *v70; // rcx
  char *v71; // rsi
  OLECHAR *v72; // rcx
  __int64 v73; // rdx
  __int64 v74; // rbx
  __int64 (__fastcall *v75)(__int64, __int64, unsigned int *); // r14
  unsigned int *v76; // rcx
  __int64 (__fastcall ***v77)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v78)(_QWORD, GUID *, unsigned int *); // r14
  unsigned int *v79; // rdi
  HRESULT v80; // eax
  int v81; // edx
  unsigned int v82; // r8d
  unsigned int *v83; // rcx
  __int64 v84; // rbx
  __int64 (__fastcall *v85)(__int64, _QWORD, unsigned int *); // rdi
  __int64 v86; // rax
  __int64 (__fastcall ***v87)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v88)(_QWORD, GUID *, unsigned int *); // rsi
  unsigned int *v89; // rdi
  HRESULT v90; // eax
  int v91; // edx
  unsigned int v92; // r8d
  unsigned int *v93; // rcx
  __int64 (__fastcall ***v94)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v95)(_QWORD, GUID *, unsigned int *); // rdi
  unsigned int *v96; // rcx
  unsigned int *v97; // rbx
  __int64 (__fastcall *v98)(unsigned int *, HSTRING *); // rdi
  PCWSTR StringRawBuffer; // rax
  unsigned int *v100; // rcx
  __int64 (__fastcall ***v101)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v102; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-58h] BYREF
  HSTRING string; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v106[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 (__fastcall ***v107)(_QWORD, GUID *, unsigned int *); // [rsp+48h] [rbp-30h] BYREF
  __int64 v108; // [rsp+50h] [rbp-28h] BYREF
  HSTRING v109; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v108 = 0;
  v107 = 0;
  *(_QWORD *)v106 = 0;
  v109 = 0;
  string = 0;
  v8 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
    __debugbreak();
  }
  ActivationFactory = ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>(
                        string,
                        &v107);
  if ( ActivationFactory < 0 )
  {
    v12 = 762;
LABEL_85:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Reporting\\AsimovScanEvents.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)hstringHeader.Reserved.Reserved1);
    goto LABEL_87;
  }
  string = 0;
  v13 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
  if ( v13 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
    __debugbreak();
  }
  v16 = string;
  v17 = v108;
  if ( v108 )
  {
    v108 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  ActivationFactory = RoGetActivationFactory(v16, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v108);
  if ( ActivationFactory < 0 )
  {
    v12 = 764;
    goto LABEL_85;
  }
  v19 = v108;
  v20 = *(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v108 + 72LL);
  v21 = *(unsigned int **)v106;
  if ( *(_QWORD *)v106 )
  {
    *(_QWORD *)v106 = 0;
    (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v21 + 16LL))(v21);
  }
  ActivationFactory = v20(v19, v18, v106);
  if ( ActivationFactory < 0 )
  {
    v12 = 767;
    goto LABEL_85;
  }
  v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v107;
  v23 = (*v107)[7];
  v24 = *(unsigned int **)v106;
  string = 0;
  v25 = WindowsCreateStringReference(L"FailedUpdatesCount", 0x12u, &hstringHeader, &string);
  if ( v25 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v25, v26, v27);
    __debugbreak();
  }
  ActivationFactory = v23(v22, (GUID *)string, v24);
  if ( ActivationFactory < 0 )
  {
    v12 = 769;
    goto LABEL_85;
  }
  v30 = *(unsigned int **)v106;
  if ( *(_QWORD *)v106 )
  {
    *(_QWORD *)v106 = 0;
    (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v30 + 16LL))(v30);
  }
  if ( a3 )
  {
    v31 = *(unsigned int **)v106;
    if ( *(_QWORD *)v106 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v31 + 16LL))(v31);
    }
    CUpdateTelemetryHelperUtil::CreateGUIDJsonArray(
      (CUpdateTelemetryHelperUtil *)a2,
      (const struct _GUID *)a3,
      (unsigned int)v106,
      v29);
    v32 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v107;
    v33 = (*v107)[7];
    v34 = *(unsigned int **)v106;
    string = 0;
    v35 = WindowsCreateStringReference(L"FailedUpdateGuids", 0x11u, &hstringHeader, &string);
    if ( v35 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v35, v36, v37);
      __debugbreak();
    }
    ActivationFactory = v33(v32, (GUID *)string, v34);
    if ( ActivationFactory < 0 )
    {
      v12 = 778;
      goto LABEL_85;
    }
    v38 = *(unsigned int **)v106;
    if ( *(_QWORD *)v106 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v38 + 16LL))(v38);
    }
  }
  v39 = (OLECHAR *)*((_QWORD *)this + 59);
  if ( v39 && SysStringLen(v39) )
  {
    v40 = v108;
    v41 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v108 + 80LL);
    v42 = *(unsigned int **)v106;
    if ( *(_QWORD *)v106 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v42 + 16LL))(v42);
    }
    v43 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (char *)this + 472);
    ActivationFactory = v41(v40, *(_QWORD *)(v43 + 24), v106);
    if ( ActivationFactory < 0 )
    {
      v12 = 784;
      goto LABEL_85;
    }
    v44 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v107;
    v45 = (*v107)[7];
    v46 = *(unsigned int **)v106;
    string = 0;
    v47 = WindowsCreateStringReference(L"ExtendedMetadataCabUrl", 0x16u, &hstringHeader, &string);
    if ( v47 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v47, v48, v49);
      __debugbreak();
    }
    ActivationFactory = v45(v44, (GUID *)string, v46);
    if ( ActivationFactory < 0 )
    {
      v12 = 786;
      goto LABEL_85;
    }
    v50 = *(unsigned int **)v106;
    if ( *(_QWORD *)v106 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v50 + 16LL))(v50);
    }
  }
  if ( *((_DWORD *)this + 114) )
  {
    v51 = v108;
    v52 = *(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v108 + 72LL);
    v53 = *(unsigned int **)v106;
    if ( *(_QWORD *)v106 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v53 + 16LL))(v53);
    }
    ActivationFactory = v52(v51, v28, v106);
    if ( ActivationFactory < 0 )
    {
      v12 = 792;
      goto LABEL_85;
    }
    v54 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v107;
    v55 = (*v107)[7];
    v56 = *(unsigned int **)v106;
    string = 0;
    v57 = WindowsCreateStringReference(L"MSIError", 8u, &hstringHeader, &string);
    if ( v57 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v57, v58, v59);
      __debugbreak();
    }
    ActivationFactory = v55(v54, (GUID *)string, v56);
    if ( ActivationFactory < 0 )
    {
      v12 = 793;
      goto LABEL_85;
    }
    v60 = *(unsigned int **)v106;
    if ( *(_QWORD *)v106 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v60 + 16LL))(v60);
    }
  }
  if ( *((_DWORD *)this + 115) )
  {
    v61 = v108;
    v62 = *(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v108 + 72LL);
    v63 = *(unsigned int **)v106;
    if ( *(_QWORD *)v106 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v63 + 16LL))(v63);
    }
    ActivationFactory = v62(v61, v28, v106);
    if ( ActivationFactory < 0 )
    {
      v12 = 799;
      goto LABEL_85;
    }
    v64 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v107;
    v65 = (*v107)[7];
    v66 = *(unsigned int **)v106;
    string = 0;
    v67 = WindowsCreateStringReference(L"DriverError", 0xBu, &hstringHeader, &string);
    if ( v67 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v67, v68, v69);
      __debugbreak();
    }
    ActivationFactory = v65(v64, (GUID *)string, v66);
    if ( ActivationFactory < 0 )
    {
      v12 = 800;
      goto LABEL_85;
    }
    v70 = *(unsigned int **)v106;
    if ( *(_QWORD *)v106 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v70 + 16LL))(v70);
    }
  }
  v71 = (char *)this + 488;
  v72 = (OLECHAR *)*((_QWORD *)this + 61);
  if ( v72 && SysStringLen(v72) )
  {
    v74 = v108;
    v75 = *(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v108 + 72LL);
    v76 = *(unsigned int **)v106;
    if ( *(_QWORD *)v106 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v76 + 16LL))(v76);
    }
    ActivationFactory = v75(v74, v73, v106);
    if ( ActivationFactory < 0 )
    {
      v12 = 806;
      goto LABEL_85;
    }
    v77 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v107;
    v78 = (*v107)[7];
    v79 = *(unsigned int **)v106;
    string = 0;
    v80 = WindowsCreateStringReference(L"CDNId", 5u, &hstringHeader, &string);
    if ( v80 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v80, v81, v82);
      JUMPOUT(0x180162EFALL);
    }
    ActivationFactory = v78(v77, (GUID *)string, v79);
    if ( ActivationFactory < 0 )
    {
      v12 = 807;
      goto LABEL_85;
    }
    v83 = *(unsigned int **)v106;
    if ( *(_QWORD *)v106 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v83 + 16LL))(v83);
      v83 = *(unsigned int **)v106;
    }
    v84 = v108;
    v85 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v108 + 80LL);
    if ( v83 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v83 + 16LL))(v83);
    }
    v86 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v71);
    ActivationFactory = v85(v84, *(_QWORD *)(v86 + 24), v106);
    if ( ActivationFactory < 0 )
    {
      v12 = 811;
      goto LABEL_85;
    }
    v87 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v107;
    v88 = (*v107)[7];
    v89 = *(unsigned int **)v106;
    string = 0;
    v90 = WindowsCreateStringReference(L"CDNCountryCode", 0xEu, &hstringHeader, &string);
    if ( v90 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v90, v91, v92);
      __debugbreak();
    }
    ActivationFactory = v88(v87, (GUID *)string, v89);
    if ( ActivationFactory < 0 )
    {
      v12 = 812;
      goto LABEL_85;
    }
    v93 = *(unsigned int **)v106;
    if ( *(_QWORD *)v106 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v93 + 16LL))(v93);
    }
  }
  v94 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v107;
  v95 = **v107;
  v96 = *(unsigned int **)v106;
  if ( *(_QWORD *)v106 )
  {
    *(_QWORD *)v106 = 0;
    (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v96 + 16LL))(v96);
  }
  ActivationFactory = v95(v94, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, v106);
  if ( ActivationFactory < 0 )
  {
    v12 = 816;
    goto LABEL_85;
  }
  v97 = *(unsigned int **)v106;
  v98 = *(__int64 (__fastcall **)(unsigned int *, HSTRING *))(**(_QWORD **)v106 + 56LL);
  WindowsDeleteString(v109);
  v109 = 0;
  ActivationFactory = v98(v97, &v109);
  if ( ActivationFactory < 0 )
  {
    v12 = 817;
    goto LABEL_85;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v109, 0);
  ActivationFactory = DuplicateString<wchar_t const *,wchar_t *>(StringRawBuffer, a4);
  if ( ActivationFactory < 0 )
  {
    v12 = 818;
    goto LABEL_85;
  }
  ActivationFactory = 0;
LABEL_87:
  WindowsDeleteString(v109);
  v109 = 0;
  v100 = *(unsigned int **)v106;
  if ( *(_QWORD *)v106 )
  {
    *(_QWORD *)v106 = 0;
    (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v100 + 16LL))(v100);
  }
  v101 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v107;
  if ( v107 )
  {
    v107 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v101)[2])(v101);
  }
  v102 = v108;
  if ( v108 )
  {
    v108 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v102 + 16LL))(v102);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180162704  push    rbp
0x180162706  push    rbx
0x180162707  push    rsi
0x180162708  push    rdi
0x180162709  push    r12
0x18016270b  push    r13
0x18016270d  push    r14
0x18016270f  push    r15
0x180162711  mov     rbp, rsp
0x180162714  sub     rsp, 78h
0x180162718  mov     rax, cs:__security_cookie
0x18016271f  xor     rax, rsp
0x180162722  mov     [rbp+var_18], rax
0x180162726  mov     r13, r9
0x180162729  mov     r14d, r8d
0x18016272c  mov     r12, rdx
0x18016272f  mov     rdi, rcx
0x180162732  xor     r15d, r15d
0x180162735  mov     [rbp+var_28], r15
0x180162739  mov     [rbp+var_30], r15
0x18016273d  mov     qword ptr [rbp+var_38], r15
0x180162741  mov     [rbp+var_20], r15
0x180162745  mov     [rbp+string], r15
0x180162749  lea     r9, [rbp+string]; string
0x18016274d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180162751  lea     edx, [r15+1Ch]; length
0x180162755  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x18016275c  call    cs:__imp_WindowsCreateStringReference
0x180162762  test    eax, eax
0x180162764  js      loc_180162EBB
0x18016276a  lea     rdx, [rbp+var_30]
0x18016276e  mov     rcx, [rbp+string]
0x180162772  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>)
0x180162777  mov     ebx, eax
0x180162779  test    eax, eax
0x18016277b  jns     short loc_180162787
0x18016277d  mov     edx, 2FAh
0x180162782  jmp     loc_180162E20
0x180162787  mov     [rbp+string], r15
0x18016278b  lea     r9, [rbp+string]; string
0x18016278f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180162793  mov     edx, 1Bh; length
0x180162798  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QB_WB; "Windows.Data.Json.JsonValue"
0x18016279f  call    cs:__imp_WindowsCreateStringReference
0x1801627a5  test    eax, eax
0x1801627a7  js      loc_180162EC3
0x1801627ad  mov     rbx, [rbp+string]
0x1801627b1  mov     rcx, [rbp+var_28]
0x1801627b5  test    rcx, rcx
0x1801627b8  jz      short loc_1801627CB
0x1801627ba  mov     [rbp+var_28], r15
0x1801627be  mov     rax, [rcx]
0x1801627c1  mov     rax, [rax+10h]
0x1801627c5  call    _guard_dispatch_icall
0x1801627ca  nop
0x1801627cb  lea     r8, [rbp+var_28]
0x1801627cf  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1801627d6  mov     rcx, rbx
0x1801627d9  call    cs:__imp_RoGetActivationFactory
0x1801627df  mov     ebx, eax
0x1801627e1  test    eax, eax
0x1801627e3  jns     short loc_1801627EF
0x1801627e5  mov     edx, 2FCh
0x1801627ea  jmp     loc_180162E20
0x1801627ef  mov     rbx, [rbp+var_28]
0x1801627f3  mov     rax, [rbx]
0x1801627f6  mov     rsi, [rax+48h]
0x1801627fa  mov     rcx, qword ptr [rbp+var_38]
0x1801627fe  test    rcx, rcx
0x180162801  jz      short loc_180162814
0x180162803  mov     qword ptr [rbp+var_38], r15
0x180162807  mov     rdx, [rcx]
0x18016280a  mov     rax, [rdx+10h]
0x18016280e  call    _guard_dispatch_icall
0x180162813  nop
0x180162814  xorps   xmm1, xmm1
0x180162817  cvtsi2sd xmm1, r14
0x18016281c  lea     r8, [rbp+var_38]
0x180162820  mov     rcx, rbx
0x180162823  mov     rax, rsi
0x180162826  call    _guard_dispatch_icall
0x18016282b  mov     ebx, eax
0x18016282d  test    eax, eax
0x18016282f  jns     short loc_18016283B
0x180162831  mov     edx, 2FFh
0x180162836  jmp     loc_180162E20
0x18016283b  mov     rbx, [rbp+var_30]
0x18016283f  mov     rax, [rbx]
0x180162842  mov     r15, [rax+38h]
0x180162846  mov     rsi, qword ptr [rbp+var_38]
0x18016284a  mov     [rbp+string], 0
0x180162852  lea     r9, [rbp+string]; string
0x180162856  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18016285a  mov     edx, 12h; length
0x18016285f  lea     rcx, aFailedupdatesc; "FailedUpdatesCount"
0x180162866  call    cs:__imp_WindowsCreateStringReference
0x18016286c  test    eax, eax
0x18016286e  js      loc_180162ECB
0x180162874  mov     r8, rsi
0x180162877  mov     rdx, [rbp+string]
0x18016287b  mov     rcx, rbx
0x18016287e  mov     rax, r15
0x180162881  call    _guard_dispatch_icall
0x180162886  mov     ebx, eax
0x180162888  xor     r15d, r15d
0x18016288b  test    eax, eax
0x18016288d  jns     short loc_180162899
0x18016288f  mov     edx, 301h
0x180162894  jmp     loc_180162E20
0x180162899  mov     rcx, qword ptr [rbp+var_38]
0x18016289d  test    rcx, rcx
0x1801628a0  jz      short loc_1801628B3
0x1801628a2  mov     qword ptr [rbp+var_38], r15
0x1801628a6  mov     rax, [rcx]
0x1801628a9  mov     rax, [rax+10h]
0x1801628ad  call    _guard_dispatch_icall
0x1801628b2  nop
0x1801628b3  test    r14d, r14d
0x1801628b6  jz      loc_180162956
0x1801628bc  mov     rcx, qword ptr [rbp+var_38]
0x1801628c0  test    rcx, rcx
0x1801628c3  jz      short loc_1801628D6
0x1801628c5  mov     qword ptr [rbp+var_38], r15
0x1801628c9  mov     rax, [rcx]
0x1801628cc  mov     rax, [rax+10h]
0x1801628d0  call    _guard_dispatch_icall
0x1801628d5  nop
0x1801628d6  lea     r8, [rbp+var_38]; unsigned int
0x1801628da  mov     edx, r14d; struct _GUID *
0x1801628dd  mov     rcx, r12; this
0x1801628e0  call    ?CreateGUIDJsonArray@CUpdateTelemetryHelperUtil@@YAJPEBU_GUID@@KPEAPEAUIJsonValue@Json@Data@Windows@ABI@@@Z; CUpdateTelemetryHelperUtil::CreateGUIDJsonArray(_GUID const *,ulong,ABI::Windows::Data::Json::IJsonValue * *)
0x1801628e5  mov     rbx, [rbp+var_30]
0x1801628e9  mov     rax, [rbx]
0x1801628ec  mov     r14, [rax+38h]
0x1801628f0  mov     rsi, qword ptr [rbp+var_38]
0x1801628f4  mov     [rbp+string], r15
0x1801628f8  lea     r9, [rbp+string]; string
0x1801628fc  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180162900  mov     edx, 11h; length
0x180162905  lea     rcx, aFailedupdategu; "FailedUpdateGuids"
0x18016290c  call    cs:__imp_WindowsCreateStringReference
0x180162912  test    eax, eax
0x180162914  js      loc_180162ED3
0x18016291a  mov     r8, rsi
0x18016291d  mov     rdx, [rbp+string]
0x180162921  mov     rcx, rbx
0x180162924  mov     rax, r14
0x180162927  call    _guard_dispatch_icall
0x18016292c  mov     ebx, eax
0x18016292e  test    eax, eax
0x180162930  jns     short loc_18016293C
0x180162932  mov     edx, 30Ah
0x180162937  jmp     loc_180162E20
0x18016293c  mov     rcx, qword ptr [rbp+var_38]
0x180162940  test    rcx, rcx
0x180162943  jz      short loc_180162956
0x180162945  mov     qword ptr [rbp+var_38], r15
0x180162949  mov     rax, [rcx]
0x18016294c  mov     rax, [rax+10h]
0x180162950  call    _guard_dispatch_icall
0x180162955  nop
0x180162956  lea     rsi, [rdi+1D8h]
0x18016295d  mov     rcx, [rsi]; pbstr
0x180162960  test    rcx, rcx
0x180162963  jz      loc_180162A3D
0x180162969  call    cs:__imp_SysStringLen
0x18016296f  test    eax, eax
0x180162971  jz      loc_180162A3D
0x180162977  mov     rbx, [rbp+var_28]
0x18016297b  mov     rax, [rbx]
0x18016297e  mov     r14, [rax+50h]
0x180162982  mov     rcx, qword ptr [rbp+var_38]
0x180162986  test    rcx, rcx
0x180162989  jz      short loc_18016299C
0x18016298b  mov     qword ptr [rbp+var_38], r15
0x18016298f  mov     rax, [rcx]
0x180162992  mov     rax, [rax+10h]
0x180162996  call    _guard_dispatch_icall
0x18016299b  nop
0x18016299c  mov     rdx, rsi
0x18016299f  lea     rcx, [rbp+hstringHeader]
0x1801629a3  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x1801629a8  nop
0x1801629a9  lea     r8, [rbp+var_38]
0x1801629ad  mov     rdx, [rax+18h]
0x1801629b1  mov     rcx, rbx
0x1801629b4  mov     rax, r14
0x1801629b7  call    _guard_dispatch_icall
0x1801629bc  mov     ebx, eax
0x1801629be  test    eax, eax
0x1801629c0  jns     short loc_1801629CC
0x1801629c2  mov     edx, 310h
0x1801629c7  jmp     loc_180162E20
0x1801629cc  mov     rbx, [rbp+var_30]
0x1801629d0  mov     rax, [rbx]
0x1801629d3  mov     r14, [rax+38h]
0x1801629d7  mov     rsi, qword ptr [rbp+var_38]
0x1801629db  mov     [rbp+string], r15
0x1801629df  lea     r9, [rbp+string]; string
0x1801629e3  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1801629e7  mov     edx, 16h; length
0x1801629ec  lea     rcx, aExtendedmetada; "ExtendedMetadataCabUrl"
0x1801629f3  call    cs:__imp_WindowsCreateStringReference
0x1801629f9  test    eax, eax
0x1801629fb  js      loc_180162EDB
0x180162a01  mov     r8, rsi
0x180162a04  mov     rdx, [rbp+string]
0x180162a08  mov     rcx, rbx
0x180162a0b  mov     rax, r14
0x180162a0e  call    _guard_dispatch_icall
0x180162a13  mov     ebx, eax
0x180162a15  test    eax, eax
0x180162a17  jns     short loc_180162A23
0x180162a19  mov     edx, 312h
0x180162a1e  jmp     loc_180162E20
0x180162a23  mov     rcx, qword ptr [rbp+var_38]
0x180162a27  test    rcx, rcx
0x180162a2a  jz      short loc_180162A3D
0x180162a2c  mov     qword ptr [rbp+var_38], r15
0x180162a30  mov     rax, [rcx]
0x180162a33  mov     rax, [rax+10h]
0x180162a37  call    _guard_dispatch_icall
0x180162a3c  nop
0x180162a3d  cmp     [rdi+1C8h], r15d
0x180162a44  jz      loc_180162B0B
0x180162a4a  mov     rbx, [rbp+var_28]
0x180162a4e  mov     rax, [rbx]
0x180162a51  mov     rsi, [rax+48h]
0x180162a55  mov     rcx, qword ptr [rbp+var_38]
0x180162a59  test    rcx, rcx
0x180162a5c  jz      short loc_180162A6F
0x180162a5e  mov     qword ptr [rbp+var_38], r15
0x180162a62  mov     rdx, [rcx]
0x180162a65  mov     rax, [rdx+10h]
0x180162a69  call    _guard_dispatch_icall
0x180162a6e  nop
0x180162a6f  movd    xmm1, dword ptr [rdi+1C8h]
0x180162a77  cvtdq2pd xmm1, xmm1
0x180162a7b  lea     r8, [rbp+var_38]
0x180162a7f  mov     rcx, rbx
0x180162a82  mov     rax, rsi
0x180162a85  call    _guard_dispatch_icall
0x180162a8a  mov     ebx, eax
0x180162a8c  test    eax, eax
0x180162a8e  jns     short loc_180162A9A
0x180162a90  mov     edx, 318h
0x180162a95  jmp     loc_180162E20
0x180162a9a  mov     rbx, [rbp+var_30]
0x180162a9e  mov     rax, [rbx]
0x180162aa1  mov     r14, [rax+38h]
0x180162aa5  mov     rsi, qword ptr [rbp+var_38]
0x180162aa9  mov     [rbp+string], r15
0x180162aad  lea     r9, [rbp+string]; string
0x180162ab1  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180162ab5  mov     edx, 8; length
0x180162aba  lea     rcx, aMsierror_1; "MSIError"
0x180162ac1  call    cs:__imp_WindowsCreateStringReference
0x180162ac7  test    eax, eax
0x180162ac9  js      loc_180162EE3
0x180162acf  mov     r8, rsi
0x180162ad2  mov     rdx, [rbp+string]
0x180162ad6  mov     rcx, rbx
0x180162ad9  mov     rax, r14
0x180162adc  call    _guard_dispatch_icall
0x180162ae1  mov     ebx, eax
0x180162ae3  test    eax, eax
0x180162ae5  jns     short loc_180162AF1
0x180162ae7  mov     edx, 319h
0x180162aec  jmp     loc_180162E20
0x180162af1  mov     rcx, qword ptr [rbp+var_38]
0x180162af5  test    rcx, rcx
0x180162af8  jz      short loc_180162B0B
0x180162afa  mov     qword ptr [rbp+var_38], r15
0x180162afe  mov     rax, [rcx]
0x180162b01  mov     rax, [rax+10h]
0x180162b05  call    _guard_dispatch_icall
0x180162b0a  nop
0x180162b0b  cmp     [rdi+1CCh], r15d
0x180162b12  jz      loc_180162BD9
0x180162b18  mov     rbx, [rbp+var_28]
0x180162b1c  mov     rax, [rbx]
0x180162b1f  mov     rsi, [rax+48h]
0x180162b23  mov     rcx, qword ptr [rbp+var_38]
0x180162b27  test    rcx, rcx
0x180162b2a  jz      short loc_180162B3D
0x180162b2c  mov     qword ptr [rbp+var_38], r15
0x180162b30  mov     rdx, [rcx]
0x180162b33  mov     rax, [rdx+10h]
0x180162b37  call    _guard_dispatch_icall
0x180162b3c  nop
0x180162b3d  movd    xmm1, dword ptr [rdi+1CCh]
0x180162b45  cvtdq2pd xmm1, xmm1
0x180162b49  lea     r8, [rbp+var_38]
0x180162b4d  mov     rcx, rbx
0x180162b50  mov     rax, rsi
0x180162b53  call    _guard_dispatch_icall
0x180162b58  mov     ebx, eax
0x180162b5a  test    eax, eax
0x180162b5c  jns     short loc_180162B68
0x180162b5e  mov     edx, 31Fh
  ... truncated ...
```
