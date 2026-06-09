# CWUTelemetryEvent::PopulateSystemInfo(CUpdateManagerReportingData *)

- ea: `0x1801702f4`
- end: `0x180170709`
- name: `?PopulateSystemInfo@CWUTelemetryEvent@@IEAAJPEAVCUpdateManagerReportingData@@@Z`
- size: `1045`
- prototype: `__int64 __fastcall(CWUTelemetryEvent *__hidden this, struct CUpdateManagerReportingData *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18016fea0`

## callees

- `0x18000def4`
- `0x18007b8a4`
- `0x180110914`
- `0x180113ae8`
- `0x18011fff0`
- `0x1801702f4`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180170340`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18017039a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18017045a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180170536`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180170340`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18017039a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18017045a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180170536`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801705f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017066a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801705f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017066a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180170632`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180170632`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801703d4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801703d4`

## string_xrefs

- `0x180170339`: `Windows.Data.Json.JsonObject`
- `0x180170393`: `Windows.Data.Json.JsonValue`
- `0x180170368`: `C:\__w\1\s\src\Client\Engine\Reporting\AsimovEventsBase.cpp`
- `0x1801703e7`: `C:\__w\1\s\src\Client\Engine\Reporting\AsimovEventsBase.cpp`
- `0x180170568`: `C:\__w\1\s\src\Client\Engine\Reporting\AsimovEventsBase.cpp`
- `0x180170655`: `C:\__w\1\s\src\Client\Engine\Reporting\AsimovEventsBase.cpp`
- `0x180170453`: `SystemProps`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
__int64 __fastcall CWUTelemetryEvent::PopulateSystemInfo(
        CWUTelemetryEvent *this,
        struct CUpdateManagerReportingData *a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int v7; // eax
  int v8; // ebx
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  HSTRING v12; // rbx
  __int64 v13; // rcx
  int ActivationFactory; // eax
  __int64 v15; // rdx
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v17)(_QWORD, GUID *, _QWORD **); // r14
  _QWORD *v18; // rdi
  HRESULT v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  __int64 v22; // rdx
  _QWORD *v23; // rcx
  __int64 v24; // rbx
  __int64 (__fastcall *v25)(__int64, __int64, _QWORD **); // rdi
  __int64 (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v27)(_QWORD, GUID *, _QWORD **); // rsi
  _QWORD *v28; // rdi
  HRESULT v29; // eax
  int v30; // edx
  unsigned int v31; // r8d
  _QWORD *v32; // rdx
  __int64 (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v34)(_QWORD, GUID *, _QWORD **); // rdi
  __int64 v35; // rdx
  _QWORD *v36; // rbx
  __int64 (__fastcall *v37)(_QWORD *, HSTRING *); // rdi
  void *v38; // rcx
  PCWSTR StringRawBuffer; // rax
  _QWORD *v40; // rcx
  __int64 v41; // rcx
  __int64 (__fastcall ***v42)(_QWORD, _QWORD, _QWORD); // rcx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  _QWORD *v46; // [rsp+40h] [rbp-30h] BYREF
  __int64 v47; // [rsp+48h] [rbp-28h] BYREF
  HSTRING v48; // [rsp+50h] [rbp-20h] BYREF
  __int64 (__fastcall ***v49)(_QWORD, GUID *, _QWORD **); // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v49 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v4 < 0 )
  {
LABEL_47:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
LABEL_48:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
    goto LABEL_49;
  }
  v7 = ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>(
         string,
         &v49);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Reporting\\AsimovEventsBase.cpp",
      (const char *)(unsigned int)v7,
      (int)hstringHeader.Reserved.Reserved1);
    goto LABEL_43;
  }
  v47 = 0;
  string = 0;
  v9 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
  if ( v9 < 0 )
    goto LABEL_48;
  v12 = string;
  v13 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  ActivationFactory = RoGetActivationFactory(v12, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v47);
  v8 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v46 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)v47 + 72LL))(
           v47,
           *((unsigned int *)a2 + 502),
           &v46);
    if ( v8 < 0 )
    {
      v15 = 145;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Reporting\\AsimovEventsBase.cpp",
        (const char *)(unsigned int)v8,
        (int)hstringHeader.Reserved.Reserved1);
      goto LABEL_39;
    }
    v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v49;
    v17 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v49)[7];
    v18 = v46;
    string = 0;
    v19 = WindowsCreateStringReference(L"SystemProps", 0xBu, &hstringHeader, &string);
    if ( v19 < 0 )
    {
LABEL_49:
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
      JUMPOUT(0x180170708LL);
    }
    v8 = v17(v16, (GUID *)string, v18);
    if ( v8 < 0 )
    {
      v15 = 146;
      goto LABEL_23;
    }
    v23 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
      v23 = v46;
    }
    v24 = v47;
    v25 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)v47 + 72LL);
    if ( v23 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
    }
    v8 = v25(v24, v22, &v46);
    if ( v8 < 0 )
    {
      v15 = 149;
      goto LABEL_23;
    }
    v26 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v49;
    v27 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v49)[7];
    v28 = v46;
    string = 0;
    v29 = WindowsCreateStringReference(L"SleepSessionId", 0xEu, &hstringHeader, &string);
    if ( v29 >= 0 )
    {
      v8 = v27(v26, (GUID *)string, v28);
      if ( v8 < 0 )
      {
        v15 = 150;
        goto LABEL_23;
      }
      v32 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
        v32 = v46;
      }
      v48 = 0;
      v33 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v49;
      v34 = **v49;
      if ( v32 )
      {
        v46 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
      }
      v8 = v34(v33, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v46);
      if ( v8 >= 0 )
      {
        v36 = v46;
        v37 = *(__int64 (__fastcall **)(_QWORD *, HSTRING *))(*v46 + 56LL);
        WindowsDeleteString(v48);
        v48 = 0;
        v8 = v37(v36, &v48);
        if ( v8 >= 0 )
        {
          v38 = (void *)*((_QWORD *)this + 13);
          if ( v38 )
          {
            SusFree(v38);
            *((_QWORD *)this + 13) = 0;
          }
          StringRawBuffer = WindowsGetStringRawBuffer(v48, 0);
          v8 = DuplicateString<wchar_t const *,wchar_t *>(StringRawBuffer, (char *)this + 104);
          if ( v8 >= 0 )
          {
            v8 = 0;
            goto LABEL_38;
          }
          v35 = 156;
        }
        else
        {
          v35 = 155;
        }
      }
      else
      {
        v35 = 154;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v35,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Reporting\\AsimovEventsBase.cpp",
        (const char *)(unsigned int)v8,
        (int)hstringHeader.Reserved.Reserved1);
LABEL_38:
      WindowsDeleteString(v48);
      v48 = 0;
LABEL_39:
      v40 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
      }
      goto LABEL_41;
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v29, v30, v31);
    goto LABEL_47;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8C,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Reporting\\AsimovEventsBase.cpp",
    (const char *)(unsigned int)ActivationFactory,
    (int)hstringHeader.Reserved.Reserved1);
LABEL_41:
  v41 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
LABEL_43:
  v42 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v49;
  if ( v49 )
  {
    v49 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v42)[2])(v42);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1801702f4  mov     [rsp-28h+arg_10], rbx
0x1801702f9  mov     [rsp-28h+arg_18], rsi
0x1801702fe  push    rbp
0x1801702ff  push    rdi
0x180170300  push    r12
0x180170302  push    r14
0x180170304  push    r15
0x180170306  mov     rbp, rsp
0x180170309  sub     rsp, 70h
0x18017030d  mov     rax, cs:__security_cookie
0x180170314  xor     rax, rsp
0x180170317  mov     [rbp+var_10], rax
0x18017031b  mov     rsi, rdx
0x18017031e  mov     r15, rcx
0x180170321  xor     r12d, r12d
0x180170324  mov     [rbp+var_18], r12
0x180170328  mov     [rbp+string], r12
0x18017032c  lea     r9, [rbp+string]; string
0x180170330  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180170334  lea     edx, [r12+1Ch]; length
0x180170339  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x180170340  call    cs:__imp_WindowsCreateStringReference
0x180170346  test    eax, eax
0x180170348  js      loc_1801706F1
0x18017034e  lea     rdx, [rbp+var_18]
0x180170352  mov     rcx, [rbp+string]
0x180170356  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>)
0x18017035b  mov     ebx, eax
0x18017035d  test    eax, eax
0x18017035f  jns     short loc_18017037E
0x180170361  mov     rcx, [rbp+28h]; this
0x180170365  mov     r9d, eax; char *
0x180170368  lea     r8, aCW1SSrcClientE_19; "C:\\__w\\1\\s\\src\\Client\\Engine\\Rep"...
0x18017036f  mov     edx, 88h; void *
0x180170374  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180170379  jmp     loc_1801706A8
0x18017037e  mov     [rbp+var_28], r12
0x180170382  mov     [rbp+string], r12
0x180170386  lea     r9, [rbp+string]; string
0x18017038a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18017038e  mov     edx, 1Bh; length
0x180170393  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QB_WB; "Windows.Data.Json.JsonValue"
0x18017039a  call    cs:__imp_WindowsCreateStringReference
0x1801703a0  test    eax, eax
0x1801703a2  js      loc_1801706F9
0x1801703a8  mov     rbx, [rbp+string]
0x1801703ac  mov     rcx, [rbp+var_28]
0x1801703b0  test    rcx, rcx
0x1801703b3  jz      short loc_1801703C6
0x1801703b5  mov     [rbp+var_28], r12
0x1801703b9  mov     rax, [rcx]
0x1801703bc  mov     rax, [rax+10h]
0x1801703c0  call    _guard_dispatch_icall
0x1801703c5  nop
0x1801703c6  lea     r8, [rbp+var_28]
0x1801703ca  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1801703d1  mov     rcx, rbx
0x1801703d4  call    cs:__imp_RoGetActivationFactory
0x1801703da  mov     ebx, eax
0x1801703dc  test    eax, eax
0x1801703de  jns     short loc_1801703FD
0x1801703e0  mov     rcx, [rbp+28h]; this
0x1801703e4  mov     r9d, eax; char *
0x1801703e7  lea     r8, aCW1SSrcClientE_19; "C:\\__w\\1\\s\\src\\Client\\Engine\\Rep"...
0x1801703ee  mov     edx, 8Ch; void *
0x1801703f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801703f8  jmp     loc_18017068E
0x1801703fd  mov     [rbp+var_30], r12
0x180170401  mov     rcx, [rbp+var_28]
0x180170405  mov     rax, [rcx]
0x180170408  mov     edx, [rsi+7D8h]
0x18017040e  xorps   xmm1, xmm1
0x180170411  cvtsi2sd xmm1, rdx
0x180170416  lea     r8, [rbp+var_30]
0x18017041a  mov     rax, [rax+48h]
0x18017041e  call    _guard_dispatch_icall
0x180170423  mov     ebx, eax
0x180170425  test    eax, eax
0x180170427  jns     short loc_180170433
0x180170429  mov     edx, 91h
0x18017042e  jmp     loc_180170561
0x180170433  mov     rbx, [rbp+var_18]
0x180170437  mov     rax, [rbx]
0x18017043a  mov     r14, [rax+38h]
0x18017043e  mov     rdi, [rbp+var_30]
0x180170442  mov     [rbp+string], r12
0x180170446  lea     r9, [rbp+string]; string
0x18017044a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18017044e  mov     edx, 0Bh; length
0x180170453  lea     rcx, aSystemprops; "SystemProps"
0x18017045a  call    cs:__imp_WindowsCreateStringReference
0x180170460  test    eax, eax
0x180170462  js      loc_180170701
0x180170468  mov     r8, rdi
0x18017046b  mov     rdx, [rbp+string]
0x18017046f  mov     rcx, rbx
0x180170472  mov     rax, r14
0x180170475  call    _guard_dispatch_icall
0x18017047a  mov     ebx, eax
0x18017047c  test    eax, eax
0x18017047e  jns     short loc_18017048A
0x180170480  mov     edx, 92h
0x180170485  jmp     loc_180170561
0x18017048a  mov     rcx, [rbp+var_30]
0x18017048e  test    rcx, rcx
0x180170491  jz      short loc_1801704A7
0x180170493  mov     [rbp+var_30], r12
0x180170497  mov     rax, [rcx]
0x18017049a  mov     rax, [rax+10h]
0x18017049e  call    _guard_dispatch_icall
0x1801704a3  mov     rcx, [rbp+var_30]
0x1801704a7  mov     rbx, [rbp+var_28]
0x1801704ab  mov     rax, [rbx]
0x1801704ae  mov     rdi, [rax+48h]
0x1801704b2  test    rcx, rcx
0x1801704b5  jz      short loc_1801704C8
0x1801704b7  mov     [rbp+var_30], r12
0x1801704bb  mov     rax, [rcx]
0x1801704be  mov     rax, [rax+10h]
0x1801704c2  call    _guard_dispatch_icall
0x1801704c7  nop
0x1801704c8  mov     rax, [rsi+7E0h]
0x1801704cf  xorps   xmm1, xmm1
0x1801704d2  test    rax, rax
0x1801704d5  js      short loc_1801704DE
0x1801704d7  cvtsi2sd xmm1, rax
0x1801704dc  jmp     short loc_1801704F3
0x1801704de  mov     rcx, rax
0x1801704e1  shr     rcx, 1
0x1801704e4  and     eax, 1
0x1801704e7  or      rcx, rax
0x1801704ea  cvtsi2sd xmm1, rcx
0x1801704ef  addsd   xmm1, xmm1
0x1801704f3  lea     r8, [rbp+var_30]
0x1801704f7  mov     rcx, rbx
0x1801704fa  mov     rax, rdi
0x1801704fd  call    _guard_dispatch_icall
0x180170502  mov     ebx, eax
0x180170504  test    eax, eax
0x180170506  jns     short loc_18017050F
0x180170508  mov     edx, 95h
0x18017050d  jmp     short loc_180170561
0x18017050f  mov     rbx, [rbp+var_18]
0x180170513  mov     rax, [rbx]
0x180170516  mov     rsi, [rax+38h]
0x18017051a  mov     rdi, [rbp+var_30]
0x18017051e  mov     [rbp+string], r12
0x180170522  lea     r9, [rbp+string]; string
0x180170526  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18017052a  mov     edx, 0Eh; length
0x18017052f  lea     rcx, aSleepsessionid; "SleepSessionId"
0x180170536  call    cs:__imp_WindowsCreateStringReference
0x18017053c  test    eax, eax
0x18017053e  js      loc_1801706E9
0x180170544  mov     r8, rdi
0x180170547  mov     rdx, [rbp+string]
0x18017054b  mov     rcx, rbx
0x18017054e  mov     rax, rsi
0x180170551  call    _guard_dispatch_icall
0x180170556  mov     ebx, eax
0x180170558  test    eax, eax
0x18017055a  jns     short loc_180170579
0x18017055c  mov     edx, 96h; void *
0x180170561  mov     rcx, [rbp+28h]; this
0x180170565  mov     r9d, ebx; char *
0x180170568  lea     r8, aCW1SSrcClientE_19; "C:\\__w\\1\\s\\src\\Client\\Engine\\Rep"...
0x18017056f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180170574  jmp     loc_180170674
0x180170579  mov     rdx, [rbp+var_30]
0x18017057d  test    rdx, rdx
0x180170580  jz      short loc_180170599
0x180170582  mov     [rbp+var_30], r12
0x180170586  mov     rax, [rdx]
0x180170589  mov     rcx, rdx
0x18017058c  mov     rax, [rax+10h]
0x180170590  call    _guard_dispatch_icall
0x180170595  mov     rdx, [rbp+var_30]
0x180170599  mov     [rbp+var_20], r12
0x18017059d  mov     rbx, [rbp+var_18]
0x1801705a1  mov     rax, [rbx]
0x1801705a4  mov     rdi, [rax]
0x1801705a7  test    rdx, rdx
0x1801705aa  jz      short loc_1801705C0
0x1801705ac  mov     [rbp+var_30], r12
0x1801705b0  mov     rcx, [rdx]
0x1801705b3  mov     rax, [rcx+10h]
0x1801705b7  mov     rcx, rdx
0x1801705ba  call    _guard_dispatch_icall
0x1801705bf  nop
0x1801705c0  lea     r8, [rbp+var_30]
0x1801705c4  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1801705cb  mov     rcx, rbx
0x1801705ce  mov     rax, rdi
0x1801705d1  call    _guard_dispatch_icall
0x1801705d6  mov     ebx, eax
0x1801705d8  test    eax, eax
0x1801705da  jns     short loc_1801705E3
0x1801705dc  mov     edx, 9Ah
0x1801705e1  jmp     short loc_18017064E
0x1801705e3  mov     rbx, [rbp+var_30]
0x1801705e7  mov     rax, [rbx]
0x1801705ea  mov     rdi, [rax+38h]
0x1801705ee  mov     rcx, [rbp+var_20]; string
0x1801705f2  call    cs:__imp_WindowsDeleteString
0x1801705f8  mov     [rbp+var_20], r12
0x1801705fc  lea     rdx, [rbp+var_20]
0x180170600  mov     rcx, rbx
0x180170603  mov     rax, rdi
0x180170606  call    _guard_dispatch_icall
0x18017060b  mov     ebx, eax
0x18017060d  test    eax, eax
0x18017060f  jns     short loc_180170618
0x180170611  mov     edx, 9Bh
0x180170616  jmp     short loc_18017064E
0x180170618  lea     rbx, [r15+68h]
0x18017061c  mov     rcx, [rbx]; lpMem
0x18017061f  test    rcx, rcx
0x180170622  jz      short loc_18017062C
0x180170624  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180170629  mov     [rbx], r12
0x18017062c  xor     edx, edx; length
0x18017062e  mov     rcx, [rbp+var_20]; string
0x180170632  call    cs:__imp_WindowsGetStringRawBuffer
0x180170638  mov     rdx, rbx
0x18017063b  mov     rcx, rax
0x18017063e  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x180170643  mov     ebx, eax
0x180170645  test    eax, eax
0x180170647  jns     short loc_180170663
0x180170649  mov     edx, 9Ch; void *
0x18017064e  mov     rcx, [rbp+28h]; this
0x180170652  mov     r9d, ebx; char *
0x180170655  lea     r8, aCW1SSrcClientE_19; "C:\\__w\\1\\s\\src\\Client\\Engine\\Rep"...
0x18017065c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180170661  jmp     short loc_180170666
0x180170663  mov     ebx, r12d
0x180170666  mov     rcx, [rbp+var_20]; string
0x18017066a  call    cs:__imp_WindowsDeleteString
0x180170670  mov     [rbp+var_20], r12
0x180170674  mov     rcx, [rbp+var_30]
0x180170678  test    rcx, rcx
0x18017067b  jz      short loc_18017068E
0x18017067d  mov     [rbp+var_30], r12
0x180170681  mov     rax, [rcx]
0x180170684  mov     rax, [rax+10h]
0x180170688  call    _guard_dispatch_icall
0x18017068d  nop
0x18017068e  mov     rcx, [rbp+var_28]
0x180170692  test    rcx, rcx
0x180170695  jz      short loc_1801706A8
0x180170697  mov     [rbp+var_28], r12
0x18017069b  mov     rax, [rcx]
0x18017069e  mov     rax, [rax+10h]
0x1801706a2  call    _guard_dispatch_icall
0x1801706a7  nop
0x1801706a8  mov     rcx, [rbp+var_18]
0x1801706ac  test    rcx, rcx
0x1801706af  jz      short loc_1801706C2
0x1801706b1  mov     [rbp+var_18], r12
0x1801706b5  mov     rdx, [rcx]
0x1801706b8  mov     rax, [rdx+10h]
0x1801706bc  call    _guard_dispatch_icall
0x1801706c1  nop
0x1801706c2  mov     eax, ebx
0x1801706c4  mov     rcx, [rbp+var_10]
0x1801706c8  xor     rcx, rsp; StackCookie
0x1801706cb  call    __security_check_cookie
0x1801706d0  lea     r11, [rsp+70h+var_s0]
0x1801706d5  mov     rbx, [r11+40h]
0x1801706d9  mov     rsi, [r11+48h]
0x1801706dd  mov     rsp, r11
0x1801706e0  pop     r15
0x1801706e2  pop     r14
0x1801706e4  pop     r12
0x1801706e6  pop     rdi
0x1801706e7  pop     rbp
0x1801706e8  retn
0x1801706e9  mov     ecx, eax; this
0x1801706eb  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1801706f0  nop
0x1801706f1  mov     ecx, eax; this
0x1801706f3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1801706f8  nop
0x1801706f9  mov     ecx, eax; this
0x1801706fb  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180170700  nop
0x180170701  mov     ecx, eax; this
0x180170703  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
