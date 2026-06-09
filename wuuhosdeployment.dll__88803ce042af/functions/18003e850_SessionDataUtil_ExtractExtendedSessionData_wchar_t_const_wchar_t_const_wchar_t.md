# SessionDataUtil::ExtractExtendedSessionData(wchar_t const *,wchar_t const *,wchar_t * *)

- ea: `0x18003e850`
- end: `0x18003eceb`
- name: `?ExtractExtendedSessionData@SessionDataUtil@@YAJPEB_W0PEAPEA_W@Z`
- size: `1179`
- prototype: `__int64 __fastcall(SessionDataUtil *__hidden this, const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003efd4`

## callees

- `0x180003950`
- `0x180009e38`
- `0x18002d674`
- `0x18002e000`
- `0x18003e850`
- `0x18003ecf4`
- `0x180041cb8`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003eb98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ec13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003eb98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ec13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ebdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ebdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e8c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e9e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e8c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e9e9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003e8e6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003e8e6`

## string_xrefs

- `0x18003e8c2`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=59
__int64 __fastcall SessionDataUtil::ExtractExtendedSessionData(
        const WCHAR *this,
        const wchar_t *a2,
        wchar_t *a3,
        wchar_t **a4)
{
  double v4; // xmm3_8
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  int ActivationFactory; // eax
  int NumberPropertyWithDefault; // ebx
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, _QWORD, JsonUtil **); // rdi
  __int64 v14; // rax
  const wchar_t *v15; // r8
  __int64 v16; // rdx
  const wchar_t *v17; // r8
  JsonUtil *v18; // rbx
  __int64 (__fastcall *v19)(JsonUtil *, HSTRING, __int64 **); // rdi
  HRESULT v20; // eax
  int v21; // edx
  unsigned int v22; // r8d
  int v23; // eax
  __int64 v24; // rdx
  unsigned int i; // edi
  __int64 v26; // rax
  int v27; // eax
  __int64 (__fastcall ***v28)(__int64, GUID *, __int64 *); // rcx
  __int64 v29; // rdx
  __int64 (__fastcall **v30)(__int64, GUID *, __int64 *); // rax
  int v31; // eax
  __int64 v32; // rbx
  __int64 (__fastcall *v33)(__int64, HSTRING *); // rdi
  int v34; // eax
  __int64 v35; // r9
  __int64 v36; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v38; // rdx
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-49h] BYREF
  HSTRING string; // [rsp+40h] [rbp-31h] BYREF
  const WCHAR *v42; // [rsp+48h] [rbp-29h] BYREF
  __int64 (__fastcall ***v43)(__int64, GUID *, __int64 *); // [rsp+50h] [rbp-21h] BYREF
  JsonUtil *v44; // [rsp+58h] [rbp-19h] BYREF
  JsonUtil *v45; // [rsp+60h] [rbp-11h] BYREF
  HSTRING v46; // [rsp+68h] [rbp-9h] BYREF
  __int64 v47; // [rsp+70h] [rbp-1h] BYREF
  __int64 *v48; // [rsp+78h] [rbp+7h] BYREF
  __int64 v49; // [rsp+80h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  v42 = a2;
  if ( !this || !*this )
  {
    v38 = 51;
    goto LABEL_64;
  }
  if ( !a2 || !*a2 )
  {
    v38 = 52;
LABEL_64:
    NumberPropertyWithDefault = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)0x80070057LL,
      (int)hstringHeader.Reserved.Reserved1);
    return (unsigned int)NumberPropertyWithDefault;
  }
  v49 = 0;
  string = 0;
  v7 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v7 < 0 )
    goto LABEL_67;
  ActivationFactory = RoGetActivationFactory(string, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v49);
  NumberPropertyWithDefault = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v45 = 0;
    v12 = v49;
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, JsonUtil **))(*(_QWORD *)v49 + 48LL);
    v45 = 0;
    v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v42);
    NumberPropertyWithDefault = v13(v12, *(_QWORD *)(v14 + 24), &v45);
    if ( NumberPropertyWithDefault < 0 )
    {
      v16 = 59;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
        (const char *)(unsigned int)NumberPropertyWithDefault,
        (int)hstringHeader.Reserved.Reserved1);
LABEL_57:
      if ( v45 )
        (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v45 + 16LL))(v45);
      goto LABEL_59;
    }
    v42 = 0;
    NumberPropertyWithDefault = JsonUtil::GetNumberPropertyWithDefault(
                                  v45,
                                  (struct ABI::Windows::Data::Json::IJsonObject *)L"Version",
                                  v15,
                                  v4,
                                  (double *)hstringHeader.Reserved.Reserved1);
    if ( NumberPropertyWithDefault < 0 )
    {
      v16 = 62;
      goto LABEL_14;
    }
    v42 = 0;
    NumberPropertyWithDefault = JsonUtil::GetNumberPropertyWithDefault(
                                  v45,
                                  (struct ABI::Windows::Data::Json::IJsonObject *)L"SchemaVersion",
                                  v17,
                                  v4,
                                  (double *)hstringHeader.Reserved.Reserved1);
    if ( NumberPropertyWithDefault < 0 )
    {
      v16 = 65;
      goto LABEL_14;
    }
    v42 = this;
    v48 = 0;
    v18 = v45;
    v19 = *(__int64 (__fastcall **)(JsonUtil *, HSTRING, __int64 **))(*(_QWORD *)v45 + 72LL);
    v48 = 0;
    string = 0;
    v20 = WindowsCreateStringReference(L"Sessions", 8u, &hstringHeader, &string);
    if ( v20 >= 0 )
    {
      v23 = v19(v18, string, &v48);
      NumberPropertyWithDefault = v23;
      v43 = 0;
      if ( v23 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          v44 = 0;
          v26 = *v48;
          v44 = 0;
          v27 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, JsonUtil **))(v26 + 48))(v48, i, &v44);
          NumberPropertyWithDefault = v27;
          if ( v27 == -2147483637 )
          {
LABEL_38:
            if ( v44 )
              (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v44 + 16LL))(v44);
            goto LABEL_40;
          }
          if ( v27 < 0 )
            break;
          v28 = v43;
          v43 = 0;
          if ( v28 )
            ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v28)[2])(v28);
          v27 = lambda_a4c2085267137ef4ce0642cdecb305f9_::operator()(&v42, v44, (__int64)&v43);
          NumberPropertyWithDefault = v27;
          if ( v27 < 0 )
          {
            v29 = 132;
            goto LABEL_35;
          }
          if ( v43 )
            goto LABEL_38;
          if ( v44 )
            (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v44 + 16LL))(v44);
        }
        v29 = 131;
LABEL_35:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v29,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
          (const char *)(unsigned int)v27,
          (int)hstringHeader.Reserved.Reserved1);
        if ( v44 )
          (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v44 + 16LL))(v44);
        goto LABEL_53;
      }
      if ( v23 != -2089484279 )
      {
        v24 = 116;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
          (const char *)(unsigned int)NumberPropertyWithDefault,
          (int)hstringHeader.Reserved.Reserved1);
LABEL_53:
        if ( v43 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v43)[2])(v43);
        if ( v48 )
          (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
        goto LABEL_57;
      }
      v43 = 0;
      NumberPropertyWithDefault = lambda_a4c2085267137ef4ce0642cdecb305f9_::operator()(&v42, v45, (__int64)&v43);
      if ( NumberPropertyWithDefault < 0 )
      {
        v24 = 117;
        goto LABEL_21;
      }
LABEL_40:
      if ( !v43 )
      {
        NumberPropertyWithDefault = 0;
        goto LABEL_53;
      }
      v47 = 0;
      v30 = *v43;
      v47 = 0;
      v31 = (*v30)((__int64)v43, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v47);
      NumberPropertyWithDefault = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x91,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
          (const char *)(unsigned int)v31,
          (int)hstringHeader.Reserved.Reserved1);
        goto LABEL_51;
      }
      v46 = 0;
      v32 = v47;
      v33 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v47 + 56LL);
      WindowsDeleteString(0);
      v46 = 0;
      v34 = v33(v32, &v46);
      NumberPropertyWithDefault = v34;
      if ( v34 >= 0 )
      {
        v42 = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(v46, 0);
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
          &v42,
          StringRawBuffer,
          -1);
        if ( v42 )
        {
          *(_QWORD *)a3 = v42;
          NumberPropertyWithDefault = 0;
          goto LABEL_50;
        }
        NumberPropertyWithDefault = -2147024882;
        v35 = 2147942414LL;
        v36 = 151;
      }
      else
      {
        v35 = (unsigned int)v34;
        v36 = 148;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
        (const char *)v35,
        (int)hstringHeader.Reserved.Reserved1);
LABEL_50:
      WindowsDeleteString(v46);
      v46 = 0;
LABEL_51:
      if ( v47 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      goto LABEL_53;
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v20, v21, v22);
LABEL_67:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
    JUMPOUT(0x18003ECEALL);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x38,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
    (const char *)(unsigned int)ActivationFactory,
    (int)hstringHeader.Reserved.Reserved1);
LABEL_59:
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  return (unsigned int)NumberPropertyWithDefault;
}

```

## disassembly

```asm
0x18003e850  mov     rax, rsp
0x18003e853  mov     [rax+8], rbx
0x18003e857  push    rbp
0x18003e858  push    rsi
0x18003e859  push    rdi
0x18003e85a  push    r14
0x18003e85c  push    r15
0x18003e85e  lea     rbp, [rax-5Fh]
0x18003e862  sub     rsp, 0A0h
0x18003e869  movaps  xmmword ptr [rax-38h], xmm6
0x18003e86d  mov     rax, cs:__security_cookie
0x18003e874  xor     rax, rsp
0x18003e877  mov     [rbp+57h+var_40], rax
0x18003e87b  mov     r14, r8
0x18003e87e  mov     rsi, rcx
0x18003e881  mov     [rbp+57h+var_80], rdx
0x18003e885  xor     r15d, r15d
0x18003e888  test    rcx, rcx
0x18003e88b  jz      loc_18003EC94
0x18003e891  cmp     [rcx], r15w
0x18003e895  jz      loc_18003EC94
0x18003e89b  test    rdx, rdx
0x18003e89e  jz      loc_18003EC8D
0x18003e8a4  cmp     [rdx], r15w
0x18003e8a8  jz      loc_18003EC8D
0x18003e8ae  mov     [rbp+57h+var_48], r15
0x18003e8b2  mov     [rbp+57h+string], r15
0x18003e8b6  lea     r9, [rbp+57h+string]; string
0x18003e8ba  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003e8be  lea     edx, [r15+1Ch]; length
0x18003e8c2  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x18003e8c9  call    cs:__imp_WindowsCreateStringReference
0x18003e8cf  test    eax, eax
0x18003e8d1  js      loc_18003ECE3
0x18003e8d7  lea     r8, [rbp+57h+var_48]
0x18003e8db  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18003e8e2  mov     rcx, [rbp+57h+string]
0x18003e8e6  call    cs:__imp_RoGetActivationFactory
0x18003e8ec  mov     ebx, eax
0x18003e8ee  test    eax, eax
0x18003e8f0  jns     short loc_18003E90E
0x18003e8f2  mov     rcx, [rbp+5Fh]; this
0x18003e8f6  mov     r9d, eax; char *
0x18003e8f9  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18003e900  lea     edx, [r15+38h]; void *
0x18003e904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e909  jmp     loc_18003EC75
0x18003e90e  mov     [rbp+57h+var_68], r15
0x18003e912  mov     rbx, [rbp+57h+var_48]
0x18003e916  mov     rax, [rbx]
0x18003e919  mov     rdi, [rax+30h]
0x18003e91d  mov     [rbp+57h+var_68], r15
0x18003e921  lea     rdx, [rbp+57h+var_80]
0x18003e925  lea     rcx, [rbp+57h+hstringHeader]
0x18003e929  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x18003e92e  nop
0x18003e92f  lea     r8, [rbp+57h+var_68]
0x18003e933  mov     rdx, [rax+18h]
0x18003e937  mov     rcx, rbx
0x18003e93a  mov     rax, rdi
0x18003e93d  call    _guard_dispatch_icall
0x18003e942  mov     ebx, eax
0x18003e944  test    eax, eax
0x18003e946  jns     short loc_18003E94F
0x18003e948  mov     edx, 3Bh ; ';'
0x18003e94d  jmp     short loc_18003E9A2
0x18003e94f  xorps   xmm6, xmm6
0x18003e952  movsd   [rbp+57h+var_80], xmm6
0x18003e957  lea     r9, [rbp+57h+var_80]
0x18003e95b  xorps   xmm2, xmm2
0x18003e95e  lea     rdx, aVersion; "Version"
0x18003e965  mov     rcx, [rbp+57h+var_68]; this
0x18003e969  call    ?GetNumberPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WNPEAN@Z; JsonUtil::GetNumberPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,double,double *)
0x18003e96e  mov     ebx, eax
0x18003e970  test    eax, eax
0x18003e972  jns     short loc_18003E97B
0x18003e974  mov     edx, 3Eh ; '>'
0x18003e979  jmp     short loc_18003E9A2
0x18003e97b  movsd   [rbp+57h+var_80], xmm6
0x18003e980  lea     r9, [rbp+57h+var_80]
0x18003e984  xorps   xmm2, xmm2
0x18003e987  lea     rdx, aSchemaversion; "SchemaVersion"
0x18003e98e  mov     rcx, [rbp+57h+var_68]; this
0x18003e992  call    ?GetNumberPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WNPEAN@Z; JsonUtil::GetNumberPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,double,double *)
0x18003e997  mov     ebx, eax
0x18003e999  test    eax, eax
0x18003e99b  jns     short loc_18003E9BA
0x18003e99d  mov     edx, 41h ; 'A'; void *
0x18003e9a2  mov     rcx, [rbp+5Fh]; this
0x18003e9a6  mov     r9d, ebx; char *
0x18003e9a9  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18003e9b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e9b5  jmp     loc_18003EC5F
0x18003e9ba  mov     [rbp+57h+var_80], rsi
0x18003e9be  mov     [rbp+57h+var_50], r15
0x18003e9c2  mov     rbx, [rbp+57h+var_68]
0x18003e9c6  mov     rax, [rbx]
0x18003e9c9  mov     rdi, [rax+48h]
0x18003e9cd  mov     [rbp+57h+var_50], r15
0x18003e9d1  mov     [rbp+57h+string], r15
0x18003e9d5  lea     r9, [rbp+57h+string]; string
0x18003e9d9  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003e9dd  mov     edx, 8; length
0x18003e9e2  lea     rcx, aSessions; "Sessions"
0x18003e9e9  call    cs:__imp_WindowsCreateStringReference
0x18003e9ef  test    eax, eax
0x18003e9f1  js      loc_18003ECDB
0x18003e9f7  lea     r8, [rbp+57h+var_50]
0x18003e9fb  mov     rdx, [rbp+57h+string]
0x18003e9ff  mov     rcx, rbx
0x18003ea02  mov     rax, rdi
0x18003ea05  call    _guard_dispatch_icall
0x18003ea0a  mov     ebx, eax
0x18003ea0c  mov     [rbp+57h+var_78], r15
0x18003ea10  test    eax, eax
0x18003ea12  jns     short loc_18003EA5E
0x18003ea14  cmp     eax, 83750009h
0x18003ea19  jz      short loc_18003EA22
0x18003ea1b  mov     edx, 74h ; 't'
0x18003ea20  jmp     short loc_18003EA46
0x18003ea22  mov     [rbp+57h+var_78], r15
0x18003ea26  lea     r8, [rbp+57h+var_78]
0x18003ea2a  mov     rdx, [rbp+57h+var_68]
0x18003ea2e  lea     rcx, [rbp+57h+var_80]
0x18003ea32  call    _lambda_a4c2085267137ef4ce0642cdecb305f9___operator__
0x18003ea37  mov     ebx, eax
0x18003ea39  test    eax, eax
0x18003ea3b  jns     loc_18003EB34
0x18003ea41  mov     edx, 75h ; 'u'; void *
0x18003ea46  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18003ea4d  mov     rcx, [rbp+5Fh]; this
0x18003ea51  mov     r9d, ebx; char *
0x18003ea54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ea59  jmp     loc_18003EC33
0x18003ea5e  mov     edi, r15d
0x18003ea61  mov     [rbp+57h+var_70], r15
0x18003ea65  mov     rcx, [rbp+57h+var_50]
0x18003ea69  mov     rax, [rcx]
0x18003ea6c  mov     [rbp+57h+var_70], r15
0x18003ea70  lea     r8, [rbp+57h+var_70]
0x18003ea74  mov     edx, edi
0x18003ea76  mov     rax, [rax+30h]
0x18003ea7a  call    _guard_dispatch_icall
0x18003ea7f  mov     ebx, eax
0x18003ea81  cmp     eax, 8000000Bh
0x18003ea86  jz      loc_18003EB1E
0x18003ea8c  test    eax, eax
0x18003ea8e  js      short loc_18003EAEA
0x18003ea90  mov     rcx, [rbp+57h+var_78]
0x18003ea94  mov     [rbp+57h+var_78], r15
0x18003ea98  test    rcx, rcx
0x18003ea9b  jz      short loc_18003EAAA
0x18003ea9d  mov     rax, [rcx]
0x18003eaa0  mov     rax, [rax+10h]
0x18003eaa4  call    _guard_dispatch_icall
0x18003eaa9  nop
0x18003eaaa  lea     r8, [rbp+57h+var_78]
0x18003eaae  mov     rdx, [rbp+57h+var_70]
0x18003eab2  lea     rcx, [rbp+57h+var_80]
0x18003eab6  call    _lambda_a4c2085267137ef4ce0642cdecb305f9___operator__
0x18003eabb  mov     ebx, eax
0x18003eabd  test    eax, eax
0x18003eabf  js      short loc_18003EAE3
0x18003eac1  cmp     [rbp+57h+var_78], r15
0x18003eac5  jnz     short loc_18003EAE1
0x18003eac7  mov     rcx, [rbp+57h+var_70]
0x18003eacb  test    rcx, rcx
0x18003eace  jz      short loc_18003EADD
0x18003ead0  mov     rax, [rcx]
0x18003ead3  mov     rax, [rax+10h]
0x18003ead7  call    _guard_dispatch_icall
0x18003eadc  nop
0x18003eadd  inc     edi
0x18003eadf  jmp     short loc_18003EA61
0x18003eae1  jmp     short loc_18003EB1E
0x18003eae3  mov     edx, 84h
0x18003eae8  jmp     short loc_18003EAEF
0x18003eaea  mov     edx, 83h; void *
0x18003eaef  mov     r9d, eax; char *
0x18003eaf2  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18003eaf9  mov     rcx, [rbp+5Fh]; this
0x18003eafd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003eb02  nop
0x18003eb03  mov     rcx, [rbp+57h+var_70]
0x18003eb07  test    rcx, rcx
0x18003eb0a  jz      short loc_18003EB19
0x18003eb0c  mov     rax, [rcx]
0x18003eb0f  mov     rax, [rax+10h]
0x18003eb13  call    _guard_dispatch_icall
0x18003eb18  nop
0x18003eb19  jmp     loc_18003EC33
0x18003eb1e  mov     rcx, [rbp+57h+var_70]
0x18003eb22  test    rcx, rcx
0x18003eb25  jz      short loc_18003EB34
0x18003eb27  mov     rax, [rcx]
0x18003eb2a  mov     rax, [rax+10h]
0x18003eb2e  call    _guard_dispatch_icall
0x18003eb33  nop
0x18003eb34  cmp     [rbp+57h+var_78], r15
0x18003eb38  jnz     short loc_18003EB42
0x18003eb3a  mov     ebx, r15d
0x18003eb3d  jmp     loc_18003EC33
0x18003eb42  mov     [rbp+57h+var_58], r15
0x18003eb46  mov     rcx, [rbp+57h+var_78]
0x18003eb4a  mov     rax, [rcx]
0x18003eb4d  mov     [rbp+57h+var_58], r15
0x18003eb51  lea     r8, [rbp+57h+var_58]
0x18003eb55  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18003eb5c  mov     rax, [rax]
0x18003eb5f  call    _guard_dispatch_icall
0x18003eb64  mov     ebx, eax
0x18003eb66  test    eax, eax
0x18003eb68  jns     short loc_18003EB87
0x18003eb6a  mov     rcx, [rbp+5Fh]; this
0x18003eb6e  mov     r9d, eax; char *
0x18003eb71  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18003eb78  mov     edx, 91h; void *
0x18003eb7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003eb82  jmp     loc_18003EC1D
0x18003eb87  mov     [rbp+57h+var_60], r15
0x18003eb8b  mov     rbx, [rbp+57h+var_58]
0x18003eb8f  mov     rax, [rbx]
0x18003eb92  mov     rdi, [rax+38h]
0x18003eb96  xor     ecx, ecx; string
0x18003eb98  call    cs:__imp_WindowsDeleteString
0x18003eb9e  mov     [rbp+57h+var_60], r15
0x18003eba2  lea     rdx, [rbp+57h+var_60]
0x18003eba6  mov     rcx, rbx
0x18003eba9  mov     rax, rdi
0x18003ebac  call    _guard_dispatch_icall
0x18003ebb1  mov     ebx, eax
0x18003ebb3  test    eax, eax
0x18003ebb5  jns     short loc_18003EBD1
0x18003ebb7  mov     r9d, eax; char *
0x18003ebba  mov     edx, 94h; void *
0x18003ebbf  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18003ebc6  mov     rcx, [rbp+5Fh]; this
0x18003ebca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ebcf  jmp     short loc_18003EC0F
0x18003ebd1  mov     [rbp+57h+var_80], r15
0x18003ebd5  xor     edx, edx; length
0x18003ebd7  mov     rcx, [rbp+57h+var_60]; string
0x18003ebdb  call    cs:__imp_WindowsGetStringRawBuffer
0x18003ebe1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003ebe5  mov     rdx, rax
0x18003ebe8  lea     rcx, [rbp+57h+var_80]
0x18003ebec  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x18003ebf1  mov     rax, [rbp+57h+var_80]
0x18003ebf5  test    rax, rax
0x18003ebf8  jnz     short loc_18003EC09
0x18003ebfa  mov     ebx, 8007000Eh
0x18003ebff  mov     r9d, ebx
0x18003ec02  mov     edx, 97h
0x18003ec07  jmp     short loc_18003EBBF
0x18003ec09  mov     [r14], rax
0x18003ec0c  mov     ebx, r15d
0x18003ec0f  mov     rcx, [rbp+57h+var_60]; string
0x18003ec13  call    cs:__imp_WindowsDeleteString
0x18003ec19  mov     [rbp+57h+var_60], r15
0x18003ec1d  mov     rcx, [rbp+57h+var_58]
0x18003ec21  test    rcx, rcx
0x18003ec24  jz      short loc_18003EC33
0x18003ec26  mov     rax, [rcx]
0x18003ec29  mov     rax, [rax+10h]
0x18003ec2d  call    _guard_dispatch_icall
0x18003ec32  nop
0x18003ec33  mov     rcx, [rbp+57h+var_78]
0x18003ec37  test    rcx, rcx
0x18003ec3a  jz      short loc_18003EC49
0x18003ec3c  mov     rax, [rcx]
0x18003ec3f  mov     rax, [rax+10h]
0x18003ec43  call    _guard_dispatch_icall
0x18003ec48  nop
0x18003ec49  mov     rcx, [rbp+57h+var_50]
0x18003ec4d  test    rcx, rcx
0x18003ec50  jz      short loc_18003EC5F
0x18003ec52  mov     rax, [rcx]
0x18003ec55  mov     rax, [rax+10h]
0x18003ec59  call    _guard_dispatch_icall
0x18003ec5e  nop
0x18003ec5f  mov     rcx, [rbp+57h+var_68]
0x18003ec63  test    rcx, rcx
0x18003ec66  jz      short loc_18003EC75
0x18003ec68  mov     rax, [rcx]
0x18003ec6b  mov     rax, [rax+10h]
0x18003ec6f  call    _guard_dispatch_icall
0x18003ec74  nop
0x18003ec75  mov     rcx, [rbp+57h+var_48]
0x18003ec79  test    rcx, rcx
0x18003ec7c  jz      short loc_18003EC8B
0x18003ec7e  mov     rdx, [rcx]
0x18003ec81  mov     rax, [rdx+10h]
0x18003ec85  call    _guard_dispatch_icall
0x18003ec8a  nop
0x18003ec8b  jmp     short loc_18003ECB1
0x18003ec8d  mov     edx, 34h ; '4'
0x18003ec92  jmp     short loc_18003EC99
0x18003ec94  mov     edx, 33h ; '3'; void *
0x18003ec99  mov     ebx, 80070057h
0x18003ec9e  mov     r9d, ebx; char *
  ... truncated ...
```
