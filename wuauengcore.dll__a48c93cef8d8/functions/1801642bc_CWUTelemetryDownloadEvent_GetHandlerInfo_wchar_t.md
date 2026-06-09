# CWUTelemetryDownloadEvent::GetHandlerInfo(wchar_t * *)

- ea: `0x1801642bc`
- end: `0x180164917`
- name: `?GetHandlerInfo@CWUTelemetryDownloadEvent@@IEAAJPEAPEA_W@Z`
- size: `1627`
- prototype: `__int64 __fastcall(CWUTelemetryDownloadEvent *__hidden this, wchar_t **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180163f60`

## callees

- `0x18000def4`
- `0x18007b8a4`
- `0x1800b30b8`
- `0x180110914`
- `0x180113ae8`
- `0x18011fff0`
- `0x180150780`
- `0x1801642bc`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1801643ba`
- `OLEAUT32!__imp_SysStringLen` at `0x1801645b1`
- `OLEAUT32!__imp_SysStringLen` at `0x1801643ba`
- `OLEAUT32!__imp_SysStringLen` at `0x1801645b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180164311`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180164353`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180164441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180164508`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180164560`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18016463f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180164747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180164311`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180164353`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180164441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180164508`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180164560`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18016463f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180164747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801647e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016484b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801647e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016484b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180164813`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180164813`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18016438d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18016438d`

## string_xrefs

- `0x18016430a`: `Windows.Data.Json.JsonObject`
- `0x18016434c`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=52
__int64 __fastcall CWUTelemetryDownloadEvent::GetHandlerInfo(CWUTelemetryDownloadEvent *this, wchar_t **a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // edi
  __int64 v8; // rdx
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  HSTRING v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rdx
  wchar_t **v15; // r8
  char *v16; // rdi
  __int64 v17; // rbx
  __int64 (__fastcall *v18)(__int64, _QWORD, _QWORD **); // rsi
  _QWORD *v19; // rcx
  __int64 v20; // rax
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v22)(_QWORD, GUID *, _QWORD **); // rsi
  _QWORD *v23; // rdi
  HRESULT v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  unsigned __int64 v27; // r9
  int v28; // eax
  int PackageFamilyNameFromPackageFullName; // eax
  unsigned int v30; // r8d
  WCHAR *v31; // rbx
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, HSTRING, _QWORD **); // r14
  _QWORD *v34; // rcx
  unsigned __int64 v35; // rdx
  HRESULT v36; // eax
  int v37; // edx
  unsigned int v38; // r8d
  __int64 v39; // rdx
  __int64 (__fastcall ***v40)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v41)(_QWORD, GUID *, _QWORD **); // r15
  _QWORD *v42; // r14
  HRESULT v43; // eax
  int v44; // edx
  unsigned int v45; // r8d
  _QWORD *v46; // rcx
  __int64 v47; // rdi
  __int64 (__fastcall *v48)(__int64, _QWORD, _QWORD **); // r14
  _QWORD *v49; // rcx
  __int64 v50; // rax
  unsigned __int64 v51; // r9
  __int64 (__fastcall ***v52)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v53)(_QWORD, GUID *, _QWORD **); // r14
  _QWORD *v54; // rsi
  HRESULT v55; // eax
  int v56; // edx
  unsigned int v57; // r8d
  int v58; // eax
  _QWORD *v59; // rcx
  __int64 v60; // rbx
  __int64 (__fastcall *v61)(__int64, __int64, _QWORD **); // rdi
  _QWORD *v62; // rcx
  int v63; // eax
  __int64 (__fastcall ***v64)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v65)(_QWORD, GUID *, _QWORD **); // rsi
  _QWORD *v66; // rdi
  HRESULT v67; // eax
  int v68; // edx
  unsigned int v69; // r8d
  _QWORD *v70; // rcx
  __int64 (__fastcall ***v71)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v72)(_QWORD, GUID *, _QWORD **); // rdi
  _QWORD *v73; // rcx
  _QWORD *v74; // rbx
  __int64 (__fastcall *v75)(_QWORD *, HSTRING *); // rdi
  PCWSTR StringRawBuffer; // rax
  _QWORD *v77; // rcx
  __int64 (__fastcall ***v78)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v79; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  PCWSTR sourceString; // [rsp+40h] [rbp-30h] BYREF
  _QWORD *v84; // [rsp+48h] [rbp-28h] BYREF
  __int64 v85; // [rsp+50h] [rbp-20h] BYREF
  __int64 (__fastcall ***v86)(_QWORD, GUID *, _QWORD **); // [rsp+58h] [rbp-18h] BYREF
  HSTRING v87; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v85 = 0;
  v86 = 0;
  v84 = 0;
  v87 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    __debugbreak();
  }
  ActivationFactory = ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>(
                        string,
                        &v86);
  if ( ActivationFactory < 0 )
  {
    v8 = 97;
LABEL_18:
    v27 = (unsigned int)ActivationFactory;
LABEL_70:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Reporting\\AsimovDownloadEvents.cpp",
      (const char *)v27,
      (int)hstringHeader.Reserved.Reserved1);
    goto LABEL_72;
  }
  string = 0;
  v9 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
  if ( v9 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
    __debugbreak();
  }
  v12 = string;
  v13 = v85;
  if ( v85 )
  {
    v85 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  ActivationFactory = RoGetActivationFactory(v12, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v85);
  if ( ActivationFactory < 0 )
  {
    v8 = 99;
    goto LABEL_18;
  }
  if ( *((_DWORD *)this + 98) == 4 )
  {
    v16 = (char *)this + 384;
    if ( SysStringLen(*((BSTR *)this + 48)) )
    {
      v17 = v85;
      v18 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)v85 + 80LL);
      v19 = v84;
      if ( v84 )
      {
        v84 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
      }
      v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v16);
      ActivationFactory = v18(v17, *(_QWORD *)(v20 + 24), &v84);
      if ( ActivationFactory < 0 )
      {
        v8 = 103;
        goto LABEL_18;
      }
      v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v86;
      v22 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v86)[7];
      v23 = v84;
      string = 0;
      v24 = WindowsCreateStringReference(L"HardwareId", 0xAu, &hstringHeader, &string);
      if ( v24 >= 0 )
      {
        ActivationFactory = v22(v21, (GUID *)string, v23);
        if ( ActivationFactory < 0 )
        {
          v8 = 104;
          goto LABEL_18;
        }
        goto LABEL_59;
      }
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
LABEL_83:
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v36, v37, v38);
      __debugbreak();
    }
  }
  v28 = *((_DWORD *)this + 98);
  if ( v28 == 9 )
  {
    sourceString = 0;
    PackageFamilyNameFromPackageFullName = CUpdateTelemetryHelperUtil::GetPackageFamilyNameFromPackageFullName(
                                             *((PCWSTR *)this + 52),
                                             (const wchar_t *)&sourceString,
                                             v15);
    v31 = (WCHAR *)sourceString;
    if ( PackageFamilyNameFromPackageFullName >= 0 )
    {
      v32 = v85;
      v33 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD **))(*(_QWORD *)v85 + 80LL);
      v34 = v84;
      if ( v84 )
      {
        v84 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
      }
      string = 0;
      v35 = -1;
      do
        ++v35;
      while ( v31[v35] );
      if ( v35 > 0xFFFFFFFF )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v35, v30);
        __debugbreak();
      }
      if ( (int)v35 + 1 < (unsigned int)v35 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v35, v30);
        __debugbreak();
      }
      v36 = WindowsCreateStringReference(v31, v35, &hstringHeader, &string);
      if ( v36 < 0 )
        goto LABEL_83;
      ActivationFactory = v33(v32, string, &v84);
      if ( ActivationFactory < 0 )
      {
        v39 = 116;
LABEL_41:
        v51 = (unsigned int)ActivationFactory;
        goto LABEL_45;
      }
      v40 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v86;
      v41 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v86)[7];
      v42 = v84;
      string = 0;
      v43 = WindowsCreateStringReference(L"PackageFamilyName", 0x11u, &hstringHeader, &string);
      if ( v43 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v43, v44, v45);
        __debugbreak();
      }
      ActivationFactory = v41(v40, (GUID *)string, v42);
      if ( ActivationFactory < 0 )
      {
        v39 = 118;
        goto LABEL_41;
      }
      v46 = v84;
      if ( v84 )
      {
        v84 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
      }
    }
    if ( SysStringLen(*((BSTR *)this + 46)) )
    {
      v47 = v85;
      v48 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)v85 + 80LL);
      v49 = v84;
      if ( v84 )
      {
        v84 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v49 + 16LL))(v49);
      }
      v50 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (char *)this + 368);
      ActivationFactory = v48(v47, *(_QWORD *)(v50 + 24), &v84);
      if ( ActivationFactory < 0 )
      {
        v39 = 124;
        goto LABEL_41;
      }
      v52 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v86;
      v53 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v86)[7];
      v54 = v84;
      string = 0;
      v55 = WindowsCreateStringReference(L"IntentPFNs", 0xAu, &hstringHeader, &string);
      if ( v55 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v55, v56, v57);
        JUMPOUT(0x180164916LL);
      }
      v58 = v53(v52, (GUID *)string, v54);
      ActivationFactory = v58;
      if ( v58 < 0 )
      {
        v51 = (unsigned int)v58;
        v39 = 125;
LABEL_45:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v39,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Reporting\\AsimovDownloadEvents.cpp",
          (const char *)v51,
          (int)hstringHeader.Reserved.Reserved1);
        if ( v31 )
          SusFree(v31);
        goto LABEL_72;
      }
      v59 = v84;
      if ( v84 )
      {
        v84 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v59 + 16LL))(v59);
      }
    }
    if ( v31 )
      SusFree(v31);
    goto LABEL_61;
  }
  if ( v28 == 8 )
  {
    v60 = v85;
    v61 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)v85 + 72LL);
    v62 = v84;
    if ( v84 )
    {
      v84 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
    }
    v63 = v61(v60, v14, &v84);
    ActivationFactory = v63;
    if ( v63 >= 0 )
    {
      v64 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v86;
      v65 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v86)[7];
      v66 = v84;
      string = 0;
      v67 = WindowsCreateStringReference(L"CbsMethod", 9u, &hstringHeader, &string);
      if ( v67 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v67, v68, v69);
        __debugbreak();
      }
      v63 = v65(v64, (GUID *)string, v66);
      ActivationFactory = v63;
      if ( v63 >= 0 )
      {
LABEL_59:
        v70 = v84;
        if ( v84 )
        {
          v84 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v70 + 16LL))(v70);
        }
        goto LABEL_61;
      }
      v8 = 133;
    }
    else
    {
      v8 = 132;
    }
LABEL_69:
    v27 = (unsigned int)v63;
    goto LABEL_70;
  }
LABEL_61:
  v71 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v86;
  v72 = **v86;
  v73 = v84;
  if ( v84 )
  {
    v84 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v73 + 16LL))(v73);
  }
  v63 = v72(v71, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v84);
  ActivationFactory = v63;
  if ( v63 < 0 )
  {
    v8 = 138;
    goto LABEL_69;
  }
  v74 = v84;
  v75 = *(__int64 (__fastcall **)(_QWORD *, HSTRING *))(*v84 + 56LL);
  WindowsDeleteString(v87);
  v87 = 0;
  v63 = v75(v74, &v87);
  ActivationFactory = v63;
  if ( v63 < 0 )
  {
    v8 = 139;
    goto LABEL_69;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v87, 0);
  v63 = DuplicateString<wchar_t const *,wchar_t *>(StringRawBuffer, a2);
  ActivationFactory = v63;
  if ( v63 < 0 )
  {
    v8 = 140;
    goto LABEL_69;
  }
  ActivationFactory = 0;
LABEL_72:
  WindowsDeleteString(v87);
  v87 = 0;
  v77 = v84;
  if ( v84 )
  {
    v84 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v77 + 16LL))(v77);
  }
  v78 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v86;
  if ( v86 )
  {
    v86 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v78)[2])(v78);
  }
  v79 = v85;
  if ( v85 )
  {
    v85 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1801642bc  mov     [rsp-38h+arg_10], rbx
0x1801642c1  push    rbp
0x1801642c2  push    rsi
0x1801642c3  push    rdi
0x1801642c4  push    r12
0x1801642c6  push    r13
0x1801642c8  push    r14
0x1801642ca  push    r15
0x1801642cc  mov     rbp, rsp
0x1801642cf  sub     rsp, 70h
0x1801642d3  mov     rax, cs:__security_cookie
0x1801642da  xor     rax, rsp
0x1801642dd  mov     [rbp+var_8], rax
0x1801642e1  mov     r12, rdx
0x1801642e4  mov     rsi, rcx
0x1801642e7  xor     r13d, r13d
0x1801642ea  mov     [rbp+var_20], r13
0x1801642ee  mov     [rbp+var_18], r13
0x1801642f2  mov     [rbp+var_28], r13
0x1801642f6  mov     [rbp+var_10], r13
0x1801642fa  mov     [rbp+string], r13
0x1801642fe  lea     r9, [rbp+string]; string
0x180164302  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180164306  lea     edx, [r13+1Ch]; length
0x18016430a  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x180164311  call    cs:__imp_WindowsCreateStringReference
0x180164317  test    eax, eax
0x180164319  js      loc_1801648D1
0x18016431f  lea     rdx, [rbp+var_18]
0x180164323  mov     rcx, [rbp+string]
0x180164327  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>)
0x18016432c  mov     edi, eax
0x18016432e  test    eax, eax
0x180164330  jns     short loc_18016433B
0x180164332  lea     edx, [r13+61h]
0x180164336  jmp     loc_18016446C
0x18016433b  mov     [rbp+string], r13
0x18016433f  lea     r9, [rbp+string]; string
0x180164343  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180164347  mov     edx, 1Bh; length
0x18016434c  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QB_WB; "Windows.Data.Json.JsonValue"
0x180164353  call    cs:__imp_WindowsCreateStringReference
0x180164359  test    eax, eax
0x18016435b  js      loc_1801648D9
0x180164361  mov     rbx, [rbp+string]
0x180164365  mov     rcx, [rbp+var_20]
0x180164369  test    rcx, rcx
0x18016436c  jz      short loc_18016437F
0x18016436e  mov     [rbp+var_20], r13
0x180164372  mov     rax, [rcx]
0x180164375  mov     rax, [rax+10h]
0x180164379  call    _guard_dispatch_icall
0x18016437e  nop
0x18016437f  lea     r8, [rbp+var_20]
0x180164383  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18016438a  mov     rcx, rbx
0x18016438d  call    cs:__imp_RoGetActivationFactory
0x180164393  mov     edi, eax
0x180164395  test    eax, eax
0x180164397  jns     short loc_1801643A3
0x180164399  mov     edx, 63h ; 'c'
0x18016439e  jmp     loc_18016446C
0x1801643a3  cmp     dword ptr [rsi+188h], 4
0x1801643aa  jnz     loc_180164479
0x1801643b0  lea     rdi, [rsi+180h]
0x1801643b7  mov     rcx, [rdi]; pbstr
0x1801643ba  call    cs:__imp_SysStringLen
0x1801643c0  test    eax, eax
0x1801643c2  jz      loc_180164479
0x1801643c8  mov     rbx, [rbp+var_20]
0x1801643cc  mov     rax, [rbx]
0x1801643cf  mov     rsi, [rax+50h]
0x1801643d3  mov     rcx, [rbp+var_28]
0x1801643d7  test    rcx, rcx
0x1801643da  jz      short loc_1801643ED
0x1801643dc  mov     [rbp+var_28], r13
0x1801643e0  mov     rax, [rcx]
0x1801643e3  mov     rax, [rax+10h]
0x1801643e7  call    _guard_dispatch_icall
0x1801643ec  nop
0x1801643ed  mov     rdx, rdi
0x1801643f0  lea     rcx, [rbp+hstringHeader]
0x1801643f4  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x1801643f9  nop
0x1801643fa  lea     r8, [rbp+var_28]
0x1801643fe  mov     rdx, [rax+18h]
0x180164402  mov     rcx, rbx
0x180164405  mov     rax, rsi
0x180164408  call    _guard_dispatch_icall
0x18016440d  mov     edi, eax
0x18016440f  test    eax, eax
0x180164411  jns     short loc_18016441A
0x180164413  mov     edx, 67h ; 'g'
0x180164418  jmp     short loc_18016446C
0x18016441a  mov     rbx, [rbp+var_18]
0x18016441e  mov     rax, [rbx]
0x180164421  mov     rsi, [rax+38h]
0x180164425  mov     rdi, [rbp+var_28]
0x180164429  mov     [rbp+string], r13
0x18016442d  lea     r9, [rbp+string]; string
0x180164431  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180164435  mov     edx, 0Ah; length
0x18016443a  lea     rcx, aHardwareid_1; "HardwareId"
0x180164441  call    cs:__imp_WindowsCreateStringReference
0x180164447  test    eax, eax
0x180164449  js      loc_1801648E1
0x18016444f  mov     r8, rdi
0x180164452  mov     rdx, [rbp+string]
0x180164456  mov     rcx, rbx
0x180164459  mov     rax, rsi
0x18016445c  call    _guard_dispatch_icall
0x180164461  mov     edi, eax
0x180164463  test    eax, eax
0x180164465  jns     short loc_180164474
0x180164467  mov     edx, 68h ; 'h'
0x18016446c  mov     r9d, edi
0x18016446f  jmp     loc_180164832
0x180164474  jmp     loc_180164777
0x180164479  mov     eax, [rsi+188h]
0x18016447f  cmp     eax, 9
0x180164482  jnz     loc_1801646C4
0x180164488  mov     [rbp+sourceString], r13
0x18016448c  lea     rdx, [rbp+sourceString]; wchar_t *
0x180164490  mov     rcx, [rsi+1A0h]; packageFullName
0x180164497  call    ?GetPackageFamilyNameFromPackageFullName@CUpdateTelemetryHelperUtil@@YAJPEB_WPEAPEA_W@Z; CUpdateTelemetryHelperUtil::GetPackageFamilyNameFromPackageFullName(wchar_t const *,wchar_t * *)
0x18016449c  mov     rbx, [rbp+sourceString]
0x1801644a0  test    eax, eax
0x1801644a2  js      loc_1801645AA
0x1801644a8  mov     rdi, [rbp+var_20]
0x1801644ac  mov     rax, [rdi]
0x1801644af  mov     r14, [rax+50h]
0x1801644b3  mov     rcx, [rbp+var_28]
0x1801644b7  test    rcx, rcx
0x1801644ba  jz      short loc_1801644CD
0x1801644bc  mov     [rbp+var_28], r13
0x1801644c0  mov     rax, [rcx]
0x1801644c3  mov     rax, [rax+10h]
0x1801644c7  call    _guard_dispatch_icall
0x1801644cc  nop
0x1801644cd  mov     [rbp+string], r13
0x1801644d1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1801644d5  inc     rdx; int
0x1801644d8  cmp     [rbx+rdx*2], r13w
0x1801644dd  jnz     short loc_1801644D5
0x1801644df  mov     eax, 0FFFFFFFFh
0x1801644e4  cmp     rdx, rax
0x1801644e7  ja      loc_180164904
0x1801644ed  lea     eax, [rdx+1]
0x1801644f0  cmp     eax, edx
0x1801644f2  jb      loc_1801648F9
0x1801644f8  ja      short loc_1801644FD
0x1801644fa  lea     edx, [rax-1]; length
0x1801644fd  lea     r9, [rbp+string]; string
0x180164501  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180164505  mov     rcx, rbx; sourceString
0x180164508  call    cs:__imp_WindowsCreateStringReference
0x18016450e  test    eax, eax
0x180164510  js      loc_1801648E9
0x180164516  lea     r8, [rbp+var_28]
0x18016451a  mov     rdx, [rbp+string]
0x18016451e  mov     rcx, rdi
0x180164521  mov     rax, r14
0x180164524  call    _guard_dispatch_icall
0x180164529  mov     edi, eax
0x18016452b  test    eax, eax
0x18016452d  jns     short loc_180164539
0x18016452f  mov     edx, 74h ; 't'
0x180164534  jmp     loc_180164613
0x180164539  mov     rdi, [rbp+var_18]
0x18016453d  mov     rax, [rdi]
0x180164540  mov     r15, [rax+38h]
0x180164544  mov     r14, [rbp+var_28]
0x180164548  mov     [rbp+string], r13
0x18016454c  lea     r9, [rbp+string]; string
0x180164550  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180164554  mov     edx, 11h; length
0x180164559  lea     rcx, aPackagefamilyn_2; "PackageFamilyName"
0x180164560  call    cs:__imp_WindowsCreateStringReference
0x180164566  test    eax, eax
0x180164568  js      loc_1801648F1
0x18016456e  mov     r8, r14
0x180164571  mov     rdx, [rbp+string]
0x180164575  mov     rcx, rdi
0x180164578  mov     rax, r15
0x18016457b  call    _guard_dispatch_icall
0x180164580  mov     edi, eax
0x180164582  test    eax, eax
0x180164584  jns     short loc_180164590
0x180164586  mov     edx, 76h ; 'v'
0x18016458b  jmp     loc_180164613
0x180164590  mov     rcx, [rbp+var_28]
0x180164594  test    rcx, rcx
0x180164597  jz      short loc_1801645AA
0x180164599  mov     [rbp+var_28], r13
0x18016459d  mov     rax, [rcx]
0x1801645a0  mov     rax, [rax+10h]
0x1801645a4  call    _guard_dispatch_icall
0x1801645a9  nop
0x1801645aa  mov     rcx, [rsi+170h]; pbstr
0x1801645b1  call    cs:__imp_SysStringLen
0x1801645b7  test    eax, eax
0x1801645b9  jz      loc_1801646AE
0x1801645bf  mov     rdi, [rbp+var_20]
0x1801645c3  mov     rax, [rdi]
0x1801645c6  mov     r14, [rax+50h]
0x1801645ca  mov     rcx, [rbp+var_28]
0x1801645ce  test    rcx, rcx
0x1801645d1  jz      short loc_1801645E4
0x1801645d3  mov     [rbp+var_28], r13
0x1801645d7  mov     rax, [rcx]
0x1801645da  mov     rax, [rax+10h]
0x1801645de  call    _guard_dispatch_icall
0x1801645e3  nop
0x1801645e4  lea     rdx, [rsi+170h]
0x1801645eb  lea     rcx, [rbp+hstringHeader]
0x1801645ef  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x1801645f4  nop
0x1801645f5  lea     r8, [rbp+var_28]
0x1801645f9  mov     rdx, [rax+18h]
0x1801645fd  mov     rcx, rdi
0x180164600  mov     rax, r14
0x180164603  call    _guard_dispatch_icall
0x180164608  mov     edi, eax
0x18016460a  test    eax, eax
0x18016460c  jns     short loc_180164618
0x18016460e  mov     edx, 7Ch ; '|'
0x180164613  mov     r9d, edi
0x180164616  jmp     short loc_18016466D
0x180164618  mov     rdi, [rbp+var_18]
0x18016461c  mov     rax, [rdi]
0x18016461f  mov     r14, [rax+38h]
0x180164623  mov     rsi, [rbp+var_28]
0x180164627  mov     [rbp+string], r13
0x18016462b  lea     r9, [rbp+string]; string
0x18016462f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180164633  mov     edx, 0Ah; length
0x180164638  lea     rcx, aIntentpfns_1; "IntentPFNs"
0x18016463f  call    cs:__imp_WindowsCreateStringReference
0x180164645  test    eax, eax
0x180164647  js      loc_18016490F
0x18016464d  mov     r8, rsi
0x180164650  mov     rdx, [rbp+string]
0x180164654  mov     rcx, rdi
0x180164657  mov     rax, r14
0x18016465a  call    _guard_dispatch_icall
0x18016465f  mov     edi, eax
0x180164661  test    eax, eax
0x180164663  jns     short loc_180164694
0x180164665  mov     r9d, eax; char *
0x180164668  mov     edx, 7Dh ; '}'; void *
0x18016466d  lea     r8, aCW1SSrcClientE_105; "C:\\__w\\1\\s\\src\\Client\\Engine\\Rep"...
0x180164674  mov     rcx, [rbp+38h]; this
0x180164678  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016467d  nop
0x18016467e  test    rbx, rbx
0x180164681  jz      loc_180164847
0x180164687  mov     rcx, rbx; lpMem
0x18016468a  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18016468f  jmp     loc_180164847
0x180164694  mov     rcx, [rbp+var_28]
0x180164698  test    rcx, rcx
0x18016469b  jz      short loc_1801646AE
0x18016469d  mov     [rbp+var_28], r13
0x1801646a1  mov     rax, [rcx]
0x1801646a4  mov     rax, [rax+10h]
0x1801646a8  call    _guard_dispatch_icall
0x1801646ad  nop
0x1801646ae  test    rbx, rbx
0x1801646b1  jz      loc_180164791
0x1801646b7  mov     rcx, rbx; lpMem
0x1801646ba  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1801646bf  jmp     loc_180164791
0x1801646c4  cmp     eax, 8
0x1801646c7  jnz     loc_180164791
0x1801646cd  mov     rbx, [rbp+var_20]
0x1801646d1  mov     rax, [rbx]
0x1801646d4  mov     rdi, [rax+48h]
0x1801646d8  mov     rcx, [rbp+var_28]
0x1801646dc  test    rcx, rcx
0x1801646df  jz      short loc_1801646F2
0x1801646e1  mov     [rbp+var_28], r13
0x1801646e5  mov     rdx, [rcx]
0x1801646e8  mov     rax, [rdx+10h]
0x1801646ec  call    _guard_dispatch_icall
0x1801646f1  nop
0x1801646f2  movzx   ecx, byte ptr [rsi+19Ch]
0x1801646f9  movd    xmm1, ecx
0x1801646fd  cvtdq2pd xmm1, xmm1
0x180164701  lea     r8, [rbp+var_28]
0x180164705  mov     rcx, rbx
0x180164708  mov     rax, rdi
0x18016470b  call    _guard_dispatch_icall
0x180164710  mov     edi, eax
0x180164712  test    eax, eax
0x180164714  jns     short loc_180164720
0x180164716  mov     edx, 84h
0x18016471b  jmp     loc_18016482F
0x180164720  mov     rbx, [rbp+var_18]
0x180164724  mov     rax, [rbx]
0x180164727  mov     rsi, [rax+38h]
  ... truncated ...
```
