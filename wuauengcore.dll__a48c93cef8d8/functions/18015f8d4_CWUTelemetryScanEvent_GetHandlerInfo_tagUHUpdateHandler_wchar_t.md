# CWUTelemetryScanEvent::GetHandlerInfo(tagUHUpdateHandler *,wchar_t * *)

- ea: `0x18015f8d4`
- end: `0x18015fd8c`
- name: `?GetHandlerInfo@CWUTelemetryScanEvent@@IEAAJPEAW4tagUHUpdateHandler@@PEAPEA_W@Z`
- size: `1208`
- prototype: `__int64 __fastcall(CWUTelemetryScanEvent *__hidden this, enum tagUHUpdateHandler *, wchar_t **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180161b00`
- `0x1801630b0`

## callees

- `0x18000def4`
- `0x18007b8a4`
- `0x1800b30b8`
- `0x180110914`
- `0x18011fff0`
- `0x18015f8d4`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18015f91d`
- `OLEAUT32!__imp_SysStringLen` at `0x18015f9e9`
- `OLEAUT32!__imp_SysStringLen` at `0x18015f91d`
- `OLEAUT32!__imp_SysStringLen` at `0x18015f9e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015f94f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015f992`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015fa6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015fb36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015fbeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015f94f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015f992`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015fa6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015fb36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015fbeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015fc8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015fcef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015fc8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015fcef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015fcb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015fcb7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18015f9cc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18015f9cc`

## string_xrefs

- `0x18015f948`: `Windows.Data.Json.JsonObject`
- `0x18015f98b`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=43
__int64 __fastcall CWUTelemetryScanEvent::GetHandlerInfo(
        CWUTelemetryScanEvent *this,
        enum tagUHUpdateHandler *a2,
        wchar_t **a3)
{
  bool v6; // zf
  char v7; // al
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
  __int64 (__fastcall *v20)(__int64, __int64, _QWORD **); // rsi
  _QWORD *v21; // rcx
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v23)(_QWORD, GUID *, _QWORD **); // r14
  _QWORD *v24; // rsi
  HRESULT v25; // eax
  int v26; // edx
  unsigned int v27; // r8d
  _QWORD *v28; // rcx
  __int64 v29; // rbx
  __int64 (__fastcall *v30)(__int64, _QWORD, _QWORD **); // rsi
  __int64 v31; // rax
  __int64 (__fastcall ***v32)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v33)(_QWORD, GUID *, _QWORD **); // rsi
  _QWORD *v34; // rdi
  HRESULT v35; // eax
  int v36; // edx
  unsigned int v37; // r8d
  __int64 v38; // rbx
  __int64 (__fastcall *v39)(__int64, __int64, _QWORD **); // rsi
  _QWORD *v40; // rcx
  __int64 (__fastcall ***v41)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v42)(_QWORD, GUID *, _QWORD **); // rsi
  _QWORD *v43; // rdi
  HRESULT v44; // eax
  int v45; // edx
  unsigned int v46; // r8d
  _QWORD *v47; // rcx
  __int64 (__fastcall ***v48)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v49)(_QWORD, GUID *, _QWORD **); // rdi
  _QWORD *v50; // rcx
  _QWORD *v51; // rbx
  __int64 (__fastcall *v52)(_QWORD *, HSTRING *); // rdi
  PCWSTR StringRawBuffer; // rax
  _QWORD *v54; // rcx
  __int64 (__fastcall ***v55)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v56; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  _QWORD *v60; // [rsp+40h] [rbp-30h] BYREF
  __int64 v61; // [rsp+48h] [rbp-28h] BYREF
  __int64 (__fastcall ***v62)(_QWORD, GUID *, _QWORD **); // [rsp+50h] [rbp-20h] BYREF
  HSTRING v63; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v61 = 0;
  v62 = 0;
  v60 = 0;
  v63 = 0;
  if ( *((_DWORD *)this + 29) || (v6 = SysStringLen(*((BSTR *)this + 53)) == 0, v7 = 0, !v6) )
    v7 = 1;
  *(_DWORD *)a2 = v7 != 0 ? 9 : -1;
  string = 0;
  v8 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
    __debugbreak();
  }
  ActivationFactory = ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>(
                        string,
                        &v62);
  if ( ActivationFactory < 0 )
  {
    v12 = 153;
LABEL_48:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Reporting\\AsimovScanEvents.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)hstringHeader.Reserved.Reserved1);
    goto LABEL_50;
  }
  string = 0;
  v13 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
  if ( v13 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
    __debugbreak();
  }
  v16 = string;
  v17 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  ActivationFactory = RoGetActivationFactory(v16, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v61);
  if ( ActivationFactory < 0 )
  {
    v12 = 155;
    goto LABEL_48;
  }
  if ( SysStringLen(*((BSTR *)this + 53)) )
  {
    v19 = v61;
    v20 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)v61 + 72LL);
    v21 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
    }
    ActivationFactory = v20(v19, v18, &v60);
    if ( ActivationFactory < 0 )
    {
      v12 = 160;
      goto LABEL_48;
    }
    v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v62;
    v23 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v62)[7];
    v24 = v60;
    string = 0;
    v25 = WindowsCreateStringReference(L"NumberOfApplicationsCategoryScanEvaluated", 0x29u, &hstringHeader, &string);
    if ( v25 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v25, v26, v27);
      __debugbreak();
    }
    ActivationFactory = v23(v22, (GUID *)string, v24);
    if ( ActivationFactory < 0 )
    {
      v12 = 161;
      goto LABEL_48;
    }
    v28 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
      v28 = v60;
    }
    v29 = v61;
    v30 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)v61 + 80LL);
    if ( v28 )
    {
      v60 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
    }
    v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (char *)this + 424);
    ActivationFactory = v30(v29, *(_QWORD *)(v31 + 24), &v60);
    if ( ActivationFactory < 0 )
    {
      v12 = 164;
      goto LABEL_48;
    }
    v32 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v62;
    v33 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v62)[7];
    v34 = v60;
    string = 0;
    v35 = WindowsCreateStringReference(L"IntentPFNs", 0xAu, &hstringHeader, &string);
    if ( v35 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v35, v36, v37);
      JUMPOUT(0x18015FD8BLL);
    }
    ActivationFactory = v33(v32, (GUID *)string, v34);
    if ( ActivationFactory < 0 )
    {
      v12 = 165;
      goto LABEL_48;
    }
  }
  else
  {
    if ( !*((_DWORD *)this + 29) )
      goto LABEL_40;
    v38 = v61;
    v39 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)v61 + 72LL);
    v40 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
    }
    ActivationFactory = v39(v38, v18, &v60);
    if ( ActivationFactory < 0 )
    {
      v12 = 173;
      goto LABEL_48;
    }
    v41 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v62;
    v42 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v62)[7];
    v43 = v60;
    string = 0;
    v44 = WindowsCreateStringReference(L"NumberOfApplicationsCategoryScanEvaluated", 0x29u, &hstringHeader, &string);
    if ( v44 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v44, v45, v46);
      __debugbreak();
    }
    ActivationFactory = v42(v41, (GUID *)string, v43);
    if ( ActivationFactory < 0 )
    {
      v12 = 175;
      goto LABEL_48;
    }
  }
  v47 = v60;
  if ( v60 )
  {
    v60 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
  }
LABEL_40:
  v48 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v62;
  v49 = **v62;
  v50 = v60;
  if ( v60 )
  {
    v60 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v50 + 16LL))(v50);
  }
  ActivationFactory = v49(v48, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v60);
  if ( ActivationFactory < 0 )
  {
    v12 = 181;
    goto LABEL_48;
  }
  v51 = v60;
  v52 = *(__int64 (__fastcall **)(_QWORD *, HSTRING *))(*v60 + 56LL);
  WindowsDeleteString(v63);
  v63 = 0;
  ActivationFactory = v52(v51, &v63);
  if ( ActivationFactory < 0 )
  {
    v12 = 182;
    goto LABEL_48;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v63, 0);
  ActivationFactory = DuplicateString<wchar_t const *,wchar_t *>(StringRawBuffer, a3);
  if ( ActivationFactory < 0 )
  {
    v12 = 183;
    goto LABEL_48;
  }
  ActivationFactory = 0;
LABEL_50:
  WindowsDeleteString(v63);
  v63 = 0;
  v54 = v60;
  if ( v60 )
  {
    v60 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v54 + 16LL))(v54);
  }
  v55 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v62;
  if ( v62 )
  {
    v62 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v55)[2])(v55);
  }
  v56 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18015f8d4  push    rbp
0x18015f8d6  push    rbx
0x18015f8d7  push    rsi
0x18015f8d8  push    rdi
0x18015f8d9  push    r12
0x18015f8db  push    r14
0x18015f8dd  push    r15
0x18015f8df  mov     rbp, rsp
0x18015f8e2  sub     rsp, 70h
0x18015f8e6  mov     rax, cs:__security_cookie
0x18015f8ed  xor     rax, rsp
0x18015f8f0  mov     [rbp+var_10], rax
0x18015f8f4  mov     r15, r8
0x18015f8f7  mov     rbx, rdx
0x18015f8fa  mov     rdi, rcx
0x18015f8fd  xor     r12d, r12d
0x18015f900  mov     [rbp+var_28], r12
0x18015f904  mov     [rbp+var_20], r12
0x18015f908  mov     [rbp+var_30], r12
0x18015f90c  mov     [rbp+var_18], r12
0x18015f910  cmp     [rcx+74h], r12d
0x18015f914  ja      short loc_18015F92A
0x18015f916  mov     rcx, [rcx+1A8h]; pbstr
0x18015f91d  call    cs:__imp_SysStringLen
0x18015f923  test    eax, eax
0x18015f925  mov     al, r12b
0x18015f928  jz      short loc_18015F92C
0x18015f92a  mov     al, 1
0x18015f92c  neg     al
0x18015f92e  sbb     eax, eax
0x18015f930  and     eax, 0Ah
0x18015f933  dec     eax
0x18015f935  mov     [rbx], eax
0x18015f937  mov     [rbp+string], r12
0x18015f93b  lea     r9, [rbp+string]; string
0x18015f93f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18015f943  mov     edx, 1Ch; length
0x18015f948  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x18015f94f  call    cs:__imp_WindowsCreateStringReference
0x18015f955  test    eax, eax
0x18015f957  js      loc_18015FD6C
0x18015f95d  lea     rdx, [rbp+var_20]
0x18015f961  mov     rcx, [rbp+string]
0x18015f965  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>)
0x18015f96a  mov     ebx, eax
0x18015f96c  test    eax, eax
0x18015f96e  jns     short loc_18015F97A
0x18015f970  mov     edx, 99h
0x18015f975  jmp     loc_18015FCD3
0x18015f97a  mov     [rbp+string], r12
0x18015f97e  lea     r9, [rbp+string]; string
0x18015f982  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18015f986  mov     edx, 1Bh; length
0x18015f98b  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QB_WB; "Windows.Data.Json.JsonValue"
0x18015f992  call    cs:__imp_WindowsCreateStringReference
0x18015f998  test    eax, eax
0x18015f99a  js      loc_18015FD74
0x18015f9a0  mov     rbx, [rbp+string]
0x18015f9a4  mov     rcx, [rbp+var_28]
0x18015f9a8  test    rcx, rcx
0x18015f9ab  jz      short loc_18015F9BE
0x18015f9ad  mov     [rbp+var_28], r12
0x18015f9b1  mov     rax, [rcx]
0x18015f9b4  mov     rax, [rax+10h]
0x18015f9b8  call    _guard_dispatch_icall
0x18015f9bd  nop
0x18015f9be  lea     r8, [rbp+var_28]
0x18015f9c2  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18015f9c9  mov     rcx, rbx
0x18015f9cc  call    cs:__imp_RoGetActivationFactory
0x18015f9d2  mov     ebx, eax
0x18015f9d4  test    eax, eax
0x18015f9d6  jns     short loc_18015F9E2
0x18015f9d8  mov     edx, 9Bh
0x18015f9dd  jmp     loc_18015FCD3
0x18015f9e2  mov     rcx, [rdi+1A8h]; pbstr
0x18015f9e9  call    cs:__imp_SysStringLen
0x18015f9ef  test    eax, eax
0x18015f9f1  jz      loc_18015FB6B
0x18015f9f7  mov     rbx, [rbp+var_28]
0x18015f9fb  mov     rax, [rbx]
0x18015f9fe  mov     rsi, [rax+48h]
0x18015fa02  mov     rcx, [rbp+var_30]
0x18015fa06  test    rcx, rcx
0x18015fa09  jz      short loc_18015FA1C
0x18015fa0b  mov     [rbp+var_30], r12
0x18015fa0f  mov     rdx, [rcx]
0x18015fa12  mov     rax, [rdx+10h]
0x18015fa16  call    _guard_dispatch_icall
0x18015fa1b  nop
0x18015fa1c  mov     ecx, [rdi+74h]
0x18015fa1f  xorps   xmm1, xmm1
0x18015fa22  cvtsi2sd xmm1, rcx
0x18015fa27  lea     r8, [rbp+var_30]
0x18015fa2b  mov     rcx, rbx
0x18015fa2e  mov     rax, rsi
0x18015fa31  call    _guard_dispatch_icall
0x18015fa36  mov     ebx, eax
0x18015fa38  test    eax, eax
0x18015fa3a  jns     short loc_18015FA46
0x18015fa3c  mov     edx, 0A0h
0x18015fa41  jmp     loc_18015FCD3
0x18015fa46  mov     rbx, [rbp+var_20]
0x18015fa4a  mov     rax, [rbx]
0x18015fa4d  mov     r14, [rax+38h]
0x18015fa51  mov     rsi, [rbp+var_30]
0x18015fa55  mov     [rbp+string], r12
0x18015fa59  lea     r9, [rbp+string]; string
0x18015fa5d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18015fa61  mov     edx, 29h ; ')'; length
0x18015fa66  lea     rcx, aNumberofapplic; "NumberOfApplicationsCategoryScanEvaluat"...
0x18015fa6d  call    cs:__imp_WindowsCreateStringReference
0x18015fa73  test    eax, eax
0x18015fa75  js      loc_18015FD7C
0x18015fa7b  mov     r8, rsi
0x18015fa7e  mov     rdx, [rbp+string]
0x18015fa82  mov     rcx, rbx
0x18015fa85  mov     rax, r14
0x18015fa88  call    _guard_dispatch_icall
0x18015fa8d  mov     ebx, eax
0x18015fa8f  test    eax, eax
0x18015fa91  jns     short loc_18015FA9D
0x18015fa93  mov     edx, 0A1h
0x18015fa98  jmp     loc_18015FCD3
0x18015fa9d  mov     rcx, [rbp+var_30]
0x18015faa1  test    rcx, rcx
0x18015faa4  jz      short loc_18015FABA
0x18015faa6  mov     [rbp+var_30], r12
0x18015faaa  mov     rax, [rcx]
0x18015faad  mov     rax, [rax+10h]
0x18015fab1  call    _guard_dispatch_icall
0x18015fab6  mov     rcx, [rbp+var_30]
0x18015faba  mov     rbx, [rbp+var_28]
0x18015fabe  mov     rax, [rbx]
0x18015fac1  mov     rsi, [rax+50h]
0x18015fac5  test    rcx, rcx
0x18015fac8  jz      short loc_18015FADB
0x18015faca  mov     [rbp+var_30], r12
0x18015face  mov     rax, [rcx]
0x18015fad1  mov     rax, [rax+10h]
0x18015fad5  call    _guard_dispatch_icall
0x18015fada  nop
0x18015fadb  lea     rdx, [rdi+1A8h]
0x18015fae2  lea     rcx, [rbp+hstringHeader]
0x18015fae6  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x18015faeb  nop
0x18015faec  lea     r8, [rbp+var_30]
0x18015faf0  mov     rdx, [rax+18h]
0x18015faf4  mov     rcx, rbx
0x18015faf7  mov     rax, rsi
0x18015fafa  call    _guard_dispatch_icall
0x18015faff  mov     ebx, eax
0x18015fb01  test    eax, eax
0x18015fb03  jns     short loc_18015FB0F
0x18015fb05  mov     edx, 0A4h
0x18015fb0a  jmp     loc_18015FCD3
0x18015fb0f  mov     rbx, [rbp+var_20]
0x18015fb13  mov     rax, [rbx]
0x18015fb16  mov     rsi, [rax+38h]
0x18015fb1a  mov     rdi, [rbp+var_30]
0x18015fb1e  mov     [rbp+string], r12
0x18015fb22  lea     r9, [rbp+string]; string
0x18015fb26  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18015fb2a  mov     edx, 0Ah; length
0x18015fb2f  lea     rcx, aIntentpfns_0; "IntentPFNs"
0x18015fb36  call    cs:__imp_WindowsCreateStringReference
0x18015fb3c  test    eax, eax
0x18015fb3e  js      loc_18015FD84
0x18015fb44  mov     r8, rdi
0x18015fb47  mov     rdx, [rbp+string]
0x18015fb4b  mov     rcx, rbx
0x18015fb4e  mov     rax, rsi
0x18015fb51  call    _guard_dispatch_icall
0x18015fb56  mov     ebx, eax
0x18015fb58  test    eax, eax
0x18015fb5a  jns     short loc_18015FB66
0x18015fb5c  mov     edx, 0A5h
0x18015fb61  jmp     loc_18015FCD3
0x18015fb66  jmp     loc_18015FC1B
0x18015fb6b  cmp     [rdi+74h], r12d
0x18015fb6f  jbe     loc_18015FC35
0x18015fb75  mov     rbx, [rbp+var_28]
0x18015fb79  mov     rax, [rbx]
0x18015fb7c  mov     rsi, [rax+48h]
0x18015fb80  mov     rcx, [rbp+var_30]
0x18015fb84  test    rcx, rcx
0x18015fb87  jz      short loc_18015FB9A
0x18015fb89  mov     [rbp+var_30], r12
0x18015fb8d  mov     rdx, [rcx]
0x18015fb90  mov     rax, [rdx+10h]
0x18015fb94  call    _guard_dispatch_icall
0x18015fb99  nop
0x18015fb9a  mov     ecx, [rdi+74h]
0x18015fb9d  xorps   xmm1, xmm1
0x18015fba0  cvtsi2sd xmm1, rcx
0x18015fba5  lea     r8, [rbp+var_30]
0x18015fba9  mov     rcx, rbx
0x18015fbac  mov     rax, rsi
0x18015fbaf  call    _guard_dispatch_icall
0x18015fbb4  mov     ebx, eax
0x18015fbb6  test    eax, eax
0x18015fbb8  jns     short loc_18015FBC4
0x18015fbba  mov     edx, 0ADh
0x18015fbbf  jmp     loc_18015FCD3
0x18015fbc4  mov     rbx, [rbp+var_20]
0x18015fbc8  mov     rax, [rbx]
0x18015fbcb  mov     rsi, [rax+38h]
0x18015fbcf  mov     rdi, [rbp+var_30]
0x18015fbd3  mov     [rbp+string], r12
0x18015fbd7  lea     r9, [rbp+string]; string
0x18015fbdb  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18015fbdf  mov     edx, 29h ; ')'; length
0x18015fbe4  lea     rcx, aNumberofapplic; "NumberOfApplicationsCategoryScanEvaluat"...
0x18015fbeb  call    cs:__imp_WindowsCreateStringReference
0x18015fbf1  test    eax, eax
0x18015fbf3  js      loc_18015FD64
0x18015fbf9  mov     r8, rdi
0x18015fbfc  mov     rdx, [rbp+string]
0x18015fc00  mov     rcx, rbx
0x18015fc03  mov     rax, rsi
0x18015fc06  call    _guard_dispatch_icall
0x18015fc0b  mov     ebx, eax
0x18015fc0d  test    eax, eax
0x18015fc0f  jns     short loc_18015FC1B
0x18015fc11  mov     edx, 0AFh
0x18015fc16  jmp     loc_18015FCD3
0x18015fc1b  mov     rcx, [rbp+var_30]
0x18015fc1f  test    rcx, rcx
0x18015fc22  jz      short loc_18015FC35
0x18015fc24  mov     [rbp+var_30], r12
0x18015fc28  mov     rax, [rcx]
0x18015fc2b  mov     rax, [rax+10h]
0x18015fc2f  call    _guard_dispatch_icall
0x18015fc34  nop
0x18015fc35  mov     rbx, [rbp+var_20]
0x18015fc39  mov     rax, [rbx]
0x18015fc3c  mov     rdi, [rax]
0x18015fc3f  mov     rcx, [rbp+var_30]
0x18015fc43  test    rcx, rcx
0x18015fc46  jz      short loc_18015FC59
0x18015fc48  mov     [rbp+var_30], r12
0x18015fc4c  mov     rdx, [rcx]
0x18015fc4f  mov     rax, [rdx+10h]
0x18015fc53  call    _guard_dispatch_icall
0x18015fc58  nop
0x18015fc59  lea     r8, [rbp+var_30]
0x18015fc5d  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18015fc64  mov     rcx, rbx
0x18015fc67  mov     rax, rdi
0x18015fc6a  call    _guard_dispatch_icall
0x18015fc6f  mov     ebx, eax
0x18015fc71  test    eax, eax
0x18015fc73  jns     short loc_18015FC7C
0x18015fc75  mov     edx, 0B5h
0x18015fc7a  jmp     short loc_18015FCD3
0x18015fc7c  mov     rbx, [rbp+var_30]
0x18015fc80  mov     rax, [rbx]
0x18015fc83  mov     rdi, [rax+38h]
0x18015fc87  mov     rcx, [rbp+var_18]; string
0x18015fc8b  call    cs:__imp_WindowsDeleteString
0x18015fc91  mov     [rbp+var_18], r12
0x18015fc95  lea     rdx, [rbp+var_18]
0x18015fc99  mov     rcx, rbx
0x18015fc9c  mov     rax, rdi
0x18015fc9f  call    _guard_dispatch_icall
0x18015fca4  mov     ebx, eax
0x18015fca6  test    eax, eax
0x18015fca8  jns     short loc_18015FCB1
0x18015fcaa  mov     edx, 0B6h
0x18015fcaf  jmp     short loc_18015FCD3
0x18015fcb1  xor     edx, edx; length
0x18015fcb3  mov     rcx, [rbp+var_18]; string
0x18015fcb7  call    cs:__imp_WindowsGetStringRawBuffer
0x18015fcbd  mov     rdx, r15
0x18015fcc0  mov     rcx, rax
0x18015fcc3  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x18015fcc8  mov     ebx, eax
0x18015fcca  test    eax, eax
0x18015fccc  jns     short loc_18015FCE8
0x18015fcce  mov     edx, 0B7h; void *
0x18015fcd3  mov     rcx, [rbp+38h]; this
0x18015fcd7  mov     r9d, ebx; char *
0x18015fcda  lea     r8, aCW1SSrcClientE_65; "C:\\__w\\1\\s\\src\\Client\\Engine\\Rep"...
0x18015fce1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015fce6  jmp     short loc_18015FCEB
0x18015fce8  mov     ebx, r12d
0x18015fceb  mov     rcx, [rbp+var_18]; string
0x18015fcef  call    cs:__imp_WindowsDeleteString
0x18015fcf5  mov     [rbp+var_18], r12
0x18015fcf9  mov     rcx, [rbp+var_30]
0x18015fcfd  test    rcx, rcx
0x18015fd00  jz      short loc_18015FD13
0x18015fd02  mov     [rbp+var_30], r12
0x18015fd06  mov     rax, [rcx]
0x18015fd09  mov     rax, [rax+10h]
0x18015fd0d  call    _guard_dispatch_icall
0x18015fd12  nop
0x18015fd13  mov     rcx, [rbp+var_20]
0x18015fd17  test    rcx, rcx
0x18015fd1a  jz      short loc_18015FD2D
  ... truncated ...
```
