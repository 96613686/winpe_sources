# SessionDataUtil::ExtractExtendedSessionData(wchar_t const *,wchar_t const *,wchar_t * *)

- ea: `0x1400151b8`
- end: `0x140015653`
- name: `?ExtractExtendedSessionData@SessionDataUtil@@YAJPEB_W0PEAPEA_W@Z`
- size: `1179`
- prototype: `__int64 __fastcall(SessionDataUtil *__hidden this, const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001593c`

## callees

- `0x140002ac0`
- `0x14000b224`
- `0x1400151b8`
- `0x14001565c`
- `0x1400182d8`
- `0x1400182f0`
- `0x1400186e8`
- `0x14001aa60`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140015500`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001557b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140015500`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001557b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140015543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140015543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140015231`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140015351`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140015231`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140015351`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001524e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001524e`

## string_xrefs

- `0x14001522a`: `Windows.Data.Json.JsonObject`

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
    JUMPOUT(0x140015652LL);
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
0x1400151b8  mov     rax, rsp
0x1400151bb  mov     [rax+8], rbx
0x1400151bf  push    rbp
0x1400151c0  push    rsi
0x1400151c1  push    rdi
0x1400151c2  push    r14
0x1400151c4  push    r15
0x1400151c6  lea     rbp, [rax-5Fh]
0x1400151ca  sub     rsp, 0A0h
0x1400151d1  movaps  xmmword ptr [rax-38h], xmm6
0x1400151d5  mov     rax, cs:__security_cookie
0x1400151dc  xor     rax, rsp
0x1400151df  mov     [rbp+57h+var_40], rax
0x1400151e3  mov     r14, r8
0x1400151e6  mov     rsi, rcx
0x1400151e9  mov     [rbp+57h+var_80], rdx
0x1400151ed  xor     r15d, r15d
0x1400151f0  test    rcx, rcx
0x1400151f3  jz      loc_1400155FC
0x1400151f9  cmp     [rcx], r15w
0x1400151fd  jz      loc_1400155FC
0x140015203  test    rdx, rdx
0x140015206  jz      loc_1400155F5
0x14001520c  cmp     [rdx], r15w
0x140015210  jz      loc_1400155F5
0x140015216  mov     [rbp+57h+var_48], r15
0x14001521a  mov     [rbp+57h+string], r15
0x14001521e  lea     r9, [rbp+57h+string]; string
0x140015222  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x140015226  lea     edx, [r15+1Ch]; length
0x14001522a  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x140015231  call    cs:__imp_WindowsCreateStringReference
0x140015237  test    eax, eax
0x140015239  js      loc_14001564B
0x14001523f  lea     r8, [rbp+57h+var_48]
0x140015243  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x14001524a  mov     rcx, [rbp+57h+string]
0x14001524e  call    cs:__imp_RoGetActivationFactory
0x140015254  mov     ebx, eax
0x140015256  test    eax, eax
0x140015258  jns     short loc_140015276
0x14001525a  mov     rcx, [rbp+5Fh]; this
0x14001525e  mov     r9d, eax; char *
0x140015261  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140015268  lea     edx, [r15+38h]; void *
0x14001526c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015271  jmp     loc_1400155DD
0x140015276  mov     [rbp+57h+var_68], r15
0x14001527a  mov     rbx, [rbp+57h+var_48]
0x14001527e  mov     rax, [rbx]
0x140015281  mov     rdi, [rax+30h]
0x140015285  mov     [rbp+57h+var_68], r15
0x140015289  lea     rdx, [rbp+57h+var_80]
0x14001528d  lea     rcx, [rbp+57h+hstringHeader]
0x140015291  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x140015296  nop
0x140015297  lea     r8, [rbp+57h+var_68]
0x14001529b  mov     rdx, [rax+18h]
0x14001529f  mov     rcx, rbx
0x1400152a2  mov     rax, rdi
0x1400152a5  call    _guard_dispatch_icall
0x1400152aa  mov     ebx, eax
0x1400152ac  test    eax, eax
0x1400152ae  jns     short loc_1400152B7
0x1400152b0  mov     edx, 3Bh ; ';'
0x1400152b5  jmp     short loc_14001530A
0x1400152b7  xorps   xmm6, xmm6
0x1400152ba  movsd   [rbp+57h+var_80], xmm6
0x1400152bf  lea     r9, [rbp+57h+var_80]
0x1400152c3  xorps   xmm2, xmm2
0x1400152c6  lea     rdx, aVersion; "Version"
0x1400152cd  mov     rcx, [rbp+57h+var_68]; this
0x1400152d1  call    ?GetNumberPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WNPEAN@Z; JsonUtil::GetNumberPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,double,double *)
0x1400152d6  mov     ebx, eax
0x1400152d8  test    eax, eax
0x1400152da  jns     short loc_1400152E3
0x1400152dc  mov     edx, 3Eh ; '>'
0x1400152e1  jmp     short loc_14001530A
0x1400152e3  movsd   [rbp+57h+var_80], xmm6
0x1400152e8  lea     r9, [rbp+57h+var_80]
0x1400152ec  xorps   xmm2, xmm2
0x1400152ef  lea     rdx, aSchemaversion; "SchemaVersion"
0x1400152f6  mov     rcx, [rbp+57h+var_68]; this
0x1400152fa  call    ?GetNumberPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WNPEAN@Z; JsonUtil::GetNumberPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,double,double *)
0x1400152ff  mov     ebx, eax
0x140015301  test    eax, eax
0x140015303  jns     short loc_140015322
0x140015305  mov     edx, 41h ; 'A'; void *
0x14001530a  mov     rcx, [rbp+5Fh]; this
0x14001530e  mov     r9d, ebx; char *
0x140015311  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140015318  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001531d  jmp     loc_1400155C7
0x140015322  mov     [rbp+57h+var_80], rsi
0x140015326  mov     [rbp+57h+var_50], r15
0x14001532a  mov     rbx, [rbp+57h+var_68]
0x14001532e  mov     rax, [rbx]
0x140015331  mov     rdi, [rax+48h]
0x140015335  mov     [rbp+57h+var_50], r15
0x140015339  mov     [rbp+57h+string], r15
0x14001533d  lea     r9, [rbp+57h+string]; string
0x140015341  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x140015345  mov     edx, 8; length
0x14001534a  lea     rcx, sourceString; "Sessions"
0x140015351  call    cs:__imp_WindowsCreateStringReference
0x140015357  test    eax, eax
0x140015359  js      loc_140015643
0x14001535f  lea     r8, [rbp+57h+var_50]
0x140015363  mov     rdx, [rbp+57h+string]
0x140015367  mov     rcx, rbx
0x14001536a  mov     rax, rdi
0x14001536d  call    _guard_dispatch_icall
0x140015372  mov     ebx, eax
0x140015374  mov     [rbp+57h+var_78], r15
0x140015378  test    eax, eax
0x14001537a  jns     short loc_1400153C6
0x14001537c  cmp     eax, 83750009h
0x140015381  jz      short loc_14001538A
0x140015383  mov     edx, 74h ; 't'
0x140015388  jmp     short loc_1400153AE
0x14001538a  mov     [rbp+57h+var_78], r15
0x14001538e  lea     r8, [rbp+57h+var_78]
0x140015392  mov     rdx, [rbp+57h+var_68]
0x140015396  lea     rcx, [rbp+57h+var_80]
0x14001539a  call    _lambda_a4c2085267137ef4ce0642cdecb305f9___operator__
0x14001539f  mov     ebx, eax
0x1400153a1  test    eax, eax
0x1400153a3  jns     loc_14001549C
0x1400153a9  mov     edx, 75h ; 'u'; void *
0x1400153ae  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400153b5  mov     rcx, [rbp+5Fh]; this
0x1400153b9  mov     r9d, ebx; char *
0x1400153bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400153c1  jmp     loc_14001559B
0x1400153c6  mov     edi, r15d
0x1400153c9  mov     [rbp+57h+var_70], r15
0x1400153cd  mov     rcx, [rbp+57h+var_50]
0x1400153d1  mov     rax, [rcx]
0x1400153d4  mov     [rbp+57h+var_70], r15
0x1400153d8  lea     r8, [rbp+57h+var_70]
0x1400153dc  mov     edx, edi
0x1400153de  mov     rax, [rax+30h]
0x1400153e2  call    _guard_dispatch_icall
0x1400153e7  mov     ebx, eax
0x1400153e9  cmp     eax, 8000000Bh
0x1400153ee  jz      loc_140015486
0x1400153f4  test    eax, eax
0x1400153f6  js      short loc_140015452
0x1400153f8  mov     rcx, [rbp+57h+var_78]
0x1400153fc  mov     [rbp+57h+var_78], r15
0x140015400  test    rcx, rcx
0x140015403  jz      short loc_140015412
0x140015405  mov     rax, [rcx]
0x140015408  mov     rax, [rax+10h]
0x14001540c  call    _guard_dispatch_icall
0x140015411  nop
0x140015412  lea     r8, [rbp+57h+var_78]
0x140015416  mov     rdx, [rbp+57h+var_70]
0x14001541a  lea     rcx, [rbp+57h+var_80]
0x14001541e  call    _lambda_a4c2085267137ef4ce0642cdecb305f9___operator__
0x140015423  mov     ebx, eax
0x140015425  test    eax, eax
0x140015427  js      short loc_14001544B
0x140015429  cmp     [rbp+57h+var_78], r15
0x14001542d  jnz     short loc_140015449
0x14001542f  mov     rcx, [rbp+57h+var_70]
0x140015433  test    rcx, rcx
0x140015436  jz      short loc_140015445
0x140015438  mov     rax, [rcx]
0x14001543b  mov     rax, [rax+10h]
0x14001543f  call    _guard_dispatch_icall
0x140015444  nop
0x140015445  inc     edi
0x140015447  jmp     short loc_1400153C9
0x140015449  jmp     short loc_140015486
0x14001544b  mov     edx, 84h
0x140015450  jmp     short loc_140015457
0x140015452  mov     edx, 83h; void *
0x140015457  mov     r9d, eax; char *
0x14001545a  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140015461  mov     rcx, [rbp+5Fh]; this
0x140015465  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001546a  nop
0x14001546b  mov     rcx, [rbp+57h+var_70]
0x14001546f  test    rcx, rcx
0x140015472  jz      short loc_140015481
0x140015474  mov     rax, [rcx]
0x140015477  mov     rax, [rax+10h]
0x14001547b  call    _guard_dispatch_icall
0x140015480  nop
0x140015481  jmp     loc_14001559B
0x140015486  mov     rcx, [rbp+57h+var_70]
0x14001548a  test    rcx, rcx
0x14001548d  jz      short loc_14001549C
0x14001548f  mov     rax, [rcx]
0x140015492  mov     rax, [rax+10h]
0x140015496  call    _guard_dispatch_icall
0x14001549b  nop
0x14001549c  cmp     [rbp+57h+var_78], r15
0x1400154a0  jnz     short loc_1400154AA
0x1400154a2  mov     ebx, r15d
0x1400154a5  jmp     loc_14001559B
0x1400154aa  mov     [rbp+57h+var_58], r15
0x1400154ae  mov     rcx, [rbp+57h+var_78]
0x1400154b2  mov     rax, [rcx]
0x1400154b5  mov     [rbp+57h+var_58], r15
0x1400154b9  lea     r8, [rbp+57h+var_58]
0x1400154bd  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1400154c4  mov     rax, [rax]
0x1400154c7  call    _guard_dispatch_icall
0x1400154cc  mov     ebx, eax
0x1400154ce  test    eax, eax
0x1400154d0  jns     short loc_1400154EF
0x1400154d2  mov     rcx, [rbp+5Fh]; this
0x1400154d6  mov     r9d, eax; char *
0x1400154d9  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400154e0  mov     edx, 91h; void *
0x1400154e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400154ea  jmp     loc_140015585
0x1400154ef  mov     [rbp+57h+var_60], r15
0x1400154f3  mov     rbx, [rbp+57h+var_58]
0x1400154f7  mov     rax, [rbx]
0x1400154fa  mov     rdi, [rax+38h]
0x1400154fe  xor     ecx, ecx; string
0x140015500  call    cs:__imp_WindowsDeleteString
0x140015506  mov     [rbp+57h+var_60], r15
0x14001550a  lea     rdx, [rbp+57h+var_60]
0x14001550e  mov     rcx, rbx
0x140015511  mov     rax, rdi
0x140015514  call    _guard_dispatch_icall
0x140015519  mov     ebx, eax
0x14001551b  test    eax, eax
0x14001551d  jns     short loc_140015539
0x14001551f  mov     r9d, eax; char *
0x140015522  mov     edx, 94h; void *
0x140015527  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14001552e  mov     rcx, [rbp+5Fh]; this
0x140015532  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015537  jmp     short loc_140015577
0x140015539  mov     [rbp+57h+var_80], r15
0x14001553d  xor     edx, edx; length
0x14001553f  mov     rcx, [rbp+57h+var_60]; string
0x140015543  call    cs:__imp_WindowsGetStringRawBuffer
0x140015549  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001554d  mov     rdx, rax
0x140015550  lea     rcx, [rbp+57h+var_80]
0x140015554  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x140015559  mov     rax, [rbp+57h+var_80]
0x14001555d  test    rax, rax
0x140015560  jnz     short loc_140015571
0x140015562  mov     ebx, 8007000Eh
0x140015567  mov     r9d, ebx
0x14001556a  mov     edx, 97h
0x14001556f  jmp     short loc_140015527
0x140015571  mov     [r14], rax
0x140015574  mov     ebx, r15d
0x140015577  mov     rcx, [rbp+57h+var_60]; string
0x14001557b  call    cs:__imp_WindowsDeleteString
0x140015581  mov     [rbp+57h+var_60], r15
0x140015585  mov     rcx, [rbp+57h+var_58]
0x140015589  test    rcx, rcx
0x14001558c  jz      short loc_14001559B
0x14001558e  mov     rax, [rcx]
0x140015591  mov     rax, [rax+10h]
0x140015595  call    _guard_dispatch_icall
0x14001559a  nop
0x14001559b  mov     rcx, [rbp+57h+var_78]
0x14001559f  test    rcx, rcx
0x1400155a2  jz      short loc_1400155B1
0x1400155a4  mov     rax, [rcx]
0x1400155a7  mov     rax, [rax+10h]
0x1400155ab  call    _guard_dispatch_icall
0x1400155b0  nop
0x1400155b1  mov     rcx, [rbp+57h+var_50]
0x1400155b5  test    rcx, rcx
0x1400155b8  jz      short loc_1400155C7
0x1400155ba  mov     rax, [rcx]
0x1400155bd  mov     rax, [rax+10h]
0x1400155c1  call    _guard_dispatch_icall
0x1400155c6  nop
0x1400155c7  mov     rcx, [rbp+57h+var_68]
0x1400155cb  test    rcx, rcx
0x1400155ce  jz      short loc_1400155DD
0x1400155d0  mov     rax, [rcx]
0x1400155d3  mov     rax, [rax+10h]
0x1400155d7  call    _guard_dispatch_icall
0x1400155dc  nop
0x1400155dd  mov     rcx, [rbp+57h+var_48]
0x1400155e1  test    rcx, rcx
0x1400155e4  jz      short loc_1400155F3
0x1400155e6  mov     rdx, [rcx]
0x1400155e9  mov     rax, [rdx+10h]
0x1400155ed  call    _guard_dispatch_icall
0x1400155f2  nop
0x1400155f3  jmp     short loc_140015619
0x1400155f5  mov     edx, 34h ; '4'
0x1400155fa  jmp     short loc_140015601
0x1400155fc  mov     edx, 33h ; '3'; void *
0x140015601  mov     ebx, 80070057h
0x140015606  mov     r9d, ebx; char *
  ... truncated ...
```
