# SessionDataUtil::ExtractExtendedSessionData(wchar_t const *,wchar_t const *,wchar_t * *)

- ea: `0x1800876b8`
- end: `0x180087b53`
- name: `?ExtractExtendedSessionData@SessionDataUtil@@YAJPEB_W0PEAPEA_W@Z`
- size: `1179`
- prototype: `__int64 __fastcall(SessionDataUtil *__hidden this, const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800508fc`
- `0x180087e30`

## callees

- `0x180006ac4`
- `0x1800876b8`
- `0x180087b5c`
- `0x180087fc4`
- `0x1800880dc`
- `0x1800880f4`
- `0x180089e48`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087a00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087a7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087a00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087a7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180087a43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180087a43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180087731`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180087851`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180087731`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180087851`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008774e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008774e`

## string_xrefs

- `0x18008772a`: `Windows.Data.Json.JsonObject`

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
          v27 = lambda_a4c2085267137ef4ce0642cdecb305f9_::operator()(&v42, v44, (const wchar_t *)&v43);
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
      NumberPropertyWithDefault = lambda_a4c2085267137ef4ce0642cdecb305f9_::operator()(&v42, v45, (const wchar_t *)&v43);
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
    JUMPOUT(0x180087B52LL);
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
0x1800876b8  mov     rax, rsp
0x1800876bb  mov     [rax+8], rbx
0x1800876bf  push    rbp
0x1800876c0  push    rsi
0x1800876c1  push    rdi
0x1800876c2  push    r14
0x1800876c4  push    r15
0x1800876c6  lea     rbp, [rax-5Fh]
0x1800876ca  sub     rsp, 0A0h
0x1800876d1  movaps  xmmword ptr [rax-38h], xmm6
0x1800876d5  mov     rax, cs:__security_cookie
0x1800876dc  xor     rax, rsp
0x1800876df  mov     [rbp+57h+var_40], rax
0x1800876e3  mov     r14, r8
0x1800876e6  mov     rsi, rcx
0x1800876e9  mov     [rbp+57h+var_80], rdx
0x1800876ed  xor     r15d, r15d
0x1800876f0  test    rcx, rcx
0x1800876f3  jz      loc_180087AFC
0x1800876f9  cmp     [rcx], r15w
0x1800876fd  jz      loc_180087AFC
0x180087703  test    rdx, rdx
0x180087706  jz      loc_180087AF5
0x18008770c  cmp     [rdx], r15w
0x180087710  jz      loc_180087AF5
0x180087716  mov     [rbp+57h+var_48], r15
0x18008771a  mov     [rbp+57h+string], r15
0x18008771e  lea     r9, [rbp+57h+string]; string
0x180087722  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180087726  lea     edx, [r15+1Ch]; length
0x18008772a  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x180087731  call    cs:__imp_WindowsCreateStringReference
0x180087737  test    eax, eax
0x180087739  js      loc_180087B4B
0x18008773f  lea     r8, [rbp+57h+var_48]
0x180087743  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18008774a  mov     rcx, [rbp+57h+string]
0x18008774e  call    cs:__imp_RoGetActivationFactory
0x180087754  mov     ebx, eax
0x180087756  test    eax, eax
0x180087758  jns     short loc_180087776
0x18008775a  mov     rcx, [rbp+5Fh]; this
0x18008775e  mov     r9d, eax; char *
0x180087761  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180087768  lea     edx, [r15+38h]; void *
0x18008776c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087771  jmp     loc_180087ADD
0x180087776  mov     [rbp+57h+var_68], r15
0x18008777a  mov     rbx, [rbp+57h+var_48]
0x18008777e  mov     rax, [rbx]
0x180087781  mov     rdi, [rax+30h]
0x180087785  mov     [rbp+57h+var_68], r15
0x180087789  lea     rdx, [rbp+57h+var_80]
0x18008778d  lea     rcx, [rbp+57h+hstringHeader]
0x180087791  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x180087796  nop
0x180087797  lea     r8, [rbp+57h+var_68]
0x18008779b  mov     rdx, [rax+18h]
0x18008779f  mov     rcx, rbx
0x1800877a2  mov     rax, rdi
0x1800877a5  call    _guard_dispatch_icall
0x1800877aa  mov     ebx, eax
0x1800877ac  test    eax, eax
0x1800877ae  jns     short loc_1800877B7
0x1800877b0  mov     edx, 3Bh ; ';'
0x1800877b5  jmp     short loc_18008780A
0x1800877b7  xorps   xmm6, xmm6
0x1800877ba  movsd   [rbp+57h+var_80], xmm6
0x1800877bf  lea     r9, [rbp+57h+var_80]
0x1800877c3  xorps   xmm2, xmm2
0x1800877c6  lea     rdx, aVersion; "Version"
0x1800877cd  mov     rcx, [rbp+57h+var_68]; this
0x1800877d1  call    ?GetNumberPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WNPEAN@Z; JsonUtil::GetNumberPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,double,double *)
0x1800877d6  mov     ebx, eax
0x1800877d8  test    eax, eax
0x1800877da  jns     short loc_1800877E3
0x1800877dc  mov     edx, 3Eh ; '>'
0x1800877e1  jmp     short loc_18008780A
0x1800877e3  movsd   [rbp+57h+var_80], xmm6
0x1800877e8  lea     r9, [rbp+57h+var_80]
0x1800877ec  xorps   xmm2, xmm2
0x1800877ef  lea     rdx, aSchemaversion; "SchemaVersion"
0x1800877f6  mov     rcx, [rbp+57h+var_68]; this
0x1800877fa  call    ?GetNumberPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WNPEAN@Z; JsonUtil::GetNumberPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,double,double *)
0x1800877ff  mov     ebx, eax
0x180087801  test    eax, eax
0x180087803  jns     short loc_180087822
0x180087805  mov     edx, 41h ; 'A'; void *
0x18008780a  mov     rcx, [rbp+5Fh]; this
0x18008780e  mov     r9d, ebx; char *
0x180087811  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180087818  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008781d  jmp     loc_180087AC7
0x180087822  mov     [rbp+57h+var_80], rsi
0x180087826  mov     [rbp+57h+var_50], r15
0x18008782a  mov     rbx, [rbp+57h+var_68]
0x18008782e  mov     rax, [rbx]
0x180087831  mov     rdi, [rax+48h]
0x180087835  mov     [rbp+57h+var_50], r15
0x180087839  mov     [rbp+57h+string], r15
0x18008783d  lea     r9, [rbp+57h+string]; string
0x180087841  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180087845  mov     edx, 8; length
0x18008784a  lea     rcx, sourceString; "Sessions"
0x180087851  call    cs:__imp_WindowsCreateStringReference
0x180087857  test    eax, eax
0x180087859  js      loc_180087B43
0x18008785f  lea     r8, [rbp+57h+var_50]
0x180087863  mov     rdx, [rbp+57h+string]
0x180087867  mov     rcx, rbx
0x18008786a  mov     rax, rdi
0x18008786d  call    _guard_dispatch_icall
0x180087872  mov     ebx, eax
0x180087874  mov     [rbp+57h+var_78], r15
0x180087878  test    eax, eax
0x18008787a  jns     short loc_1800878C6
0x18008787c  cmp     eax, 83750009h
0x180087881  jz      short loc_18008788A
0x180087883  mov     edx, 74h ; 't'
0x180087888  jmp     short loc_1800878AE
0x18008788a  mov     [rbp+57h+var_78], r15
0x18008788e  lea     r8, [rbp+57h+var_78]
0x180087892  mov     rdx, [rbp+57h+var_68]
0x180087896  lea     rcx, [rbp+57h+var_80]
0x18008789a  call    _lambda_a4c2085267137ef4ce0642cdecb305f9___operator__
0x18008789f  mov     ebx, eax
0x1800878a1  test    eax, eax
0x1800878a3  jns     loc_18008799C
0x1800878a9  mov     edx, 75h ; 'u'; void *
0x1800878ae  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800878b5  mov     rcx, [rbp+5Fh]; this
0x1800878b9  mov     r9d, ebx; char *
0x1800878bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800878c1  jmp     loc_180087A9B
0x1800878c6  mov     edi, r15d
0x1800878c9  mov     [rbp+57h+var_70], r15
0x1800878cd  mov     rcx, [rbp+57h+var_50]
0x1800878d1  mov     rax, [rcx]
0x1800878d4  mov     [rbp+57h+var_70], r15
0x1800878d8  lea     r8, [rbp+57h+var_70]
0x1800878dc  mov     edx, edi
0x1800878de  mov     rax, [rax+30h]
0x1800878e2  call    _guard_dispatch_icall
0x1800878e7  mov     ebx, eax
0x1800878e9  cmp     eax, 8000000Bh
0x1800878ee  jz      loc_180087986
0x1800878f4  test    eax, eax
0x1800878f6  js      short loc_180087952
0x1800878f8  mov     rcx, [rbp+57h+var_78]
0x1800878fc  mov     [rbp+57h+var_78], r15
0x180087900  test    rcx, rcx
0x180087903  jz      short loc_180087912
0x180087905  mov     rax, [rcx]
0x180087908  mov     rax, [rax+10h]
0x18008790c  call    _guard_dispatch_icall
0x180087911  nop
0x180087912  lea     r8, [rbp+57h+var_78]
0x180087916  mov     rdx, [rbp+57h+var_70]
0x18008791a  lea     rcx, [rbp+57h+var_80]
0x18008791e  call    _lambda_a4c2085267137ef4ce0642cdecb305f9___operator__
0x180087923  mov     ebx, eax
0x180087925  test    eax, eax
0x180087927  js      short loc_18008794B
0x180087929  cmp     [rbp+57h+var_78], r15
0x18008792d  jnz     short loc_180087949
0x18008792f  mov     rcx, [rbp+57h+var_70]
0x180087933  test    rcx, rcx
0x180087936  jz      short loc_180087945
0x180087938  mov     rax, [rcx]
0x18008793b  mov     rax, [rax+10h]
0x18008793f  call    _guard_dispatch_icall
0x180087944  nop
0x180087945  inc     edi
0x180087947  jmp     short loc_1800878C9
0x180087949  jmp     short loc_180087986
0x18008794b  mov     edx, 84h
0x180087950  jmp     short loc_180087957
0x180087952  mov     edx, 83h; void *
0x180087957  mov     r9d, eax; char *
0x18008795a  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180087961  mov     rcx, [rbp+5Fh]; this
0x180087965  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008796a  nop
0x18008796b  mov     rcx, [rbp+57h+var_70]
0x18008796f  test    rcx, rcx
0x180087972  jz      short loc_180087981
0x180087974  mov     rax, [rcx]
0x180087977  mov     rax, [rax+10h]
0x18008797b  call    _guard_dispatch_icall
0x180087980  nop
0x180087981  jmp     loc_180087A9B
0x180087986  mov     rcx, [rbp+57h+var_70]
0x18008798a  test    rcx, rcx
0x18008798d  jz      short loc_18008799C
0x18008798f  mov     rax, [rcx]
0x180087992  mov     rax, [rax+10h]
0x180087996  call    _guard_dispatch_icall
0x18008799b  nop
0x18008799c  cmp     [rbp+57h+var_78], r15
0x1800879a0  jnz     short loc_1800879AA
0x1800879a2  mov     ebx, r15d
0x1800879a5  jmp     loc_180087A9B
0x1800879aa  mov     [rbp+57h+var_58], r15
0x1800879ae  mov     rcx, [rbp+57h+var_78]
0x1800879b2  mov     rax, [rcx]
0x1800879b5  mov     [rbp+57h+var_58], r15
0x1800879b9  lea     r8, [rbp+57h+var_58]
0x1800879bd  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1800879c4  mov     rax, [rax]
0x1800879c7  call    _guard_dispatch_icall
0x1800879cc  mov     ebx, eax
0x1800879ce  test    eax, eax
0x1800879d0  jns     short loc_1800879EF
0x1800879d2  mov     rcx, [rbp+5Fh]; this
0x1800879d6  mov     r9d, eax; char *
0x1800879d9  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800879e0  mov     edx, 91h; void *
0x1800879e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800879ea  jmp     loc_180087A85
0x1800879ef  mov     [rbp+57h+var_60], r15
0x1800879f3  mov     rbx, [rbp+57h+var_58]
0x1800879f7  mov     rax, [rbx]
0x1800879fa  mov     rdi, [rax+38h]
0x1800879fe  xor     ecx, ecx; string
0x180087a00  call    cs:__imp_WindowsDeleteString
0x180087a06  mov     [rbp+57h+var_60], r15
0x180087a0a  lea     rdx, [rbp+57h+var_60]
0x180087a0e  mov     rcx, rbx
0x180087a11  mov     rax, rdi
0x180087a14  call    _guard_dispatch_icall
0x180087a19  mov     ebx, eax
0x180087a1b  test    eax, eax
0x180087a1d  jns     short loc_180087A39
0x180087a1f  mov     r9d, eax; char *
0x180087a22  mov     edx, 94h; void *
0x180087a27  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180087a2e  mov     rcx, [rbp+5Fh]; this
0x180087a32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087a37  jmp     short loc_180087A77
0x180087a39  mov     [rbp+57h+var_80], r15
0x180087a3d  xor     edx, edx; length
0x180087a3f  mov     rcx, [rbp+57h+var_60]; string
0x180087a43  call    cs:__imp_WindowsGetStringRawBuffer
0x180087a49  or      r8, 0FFFFFFFFFFFFFFFFh
0x180087a4d  mov     rdx, rax
0x180087a50  lea     rcx, [rbp+57h+var_80]
0x180087a54  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x180087a59  mov     rax, [rbp+57h+var_80]
0x180087a5d  test    rax, rax
0x180087a60  jnz     short loc_180087A71
0x180087a62  mov     ebx, 8007000Eh
0x180087a67  mov     r9d, ebx
0x180087a6a  mov     edx, 97h
0x180087a6f  jmp     short loc_180087A27
0x180087a71  mov     [r14], rax
0x180087a74  mov     ebx, r15d
0x180087a77  mov     rcx, [rbp+57h+var_60]; string
0x180087a7b  call    cs:__imp_WindowsDeleteString
0x180087a81  mov     [rbp+57h+var_60], r15
0x180087a85  mov     rcx, [rbp+57h+var_58]
0x180087a89  test    rcx, rcx
0x180087a8c  jz      short loc_180087A9B
0x180087a8e  mov     rax, [rcx]
0x180087a91  mov     rax, [rax+10h]
0x180087a95  call    _guard_dispatch_icall
0x180087a9a  nop
0x180087a9b  mov     rcx, [rbp+57h+var_78]
0x180087a9f  test    rcx, rcx
0x180087aa2  jz      short loc_180087AB1
0x180087aa4  mov     rax, [rcx]
0x180087aa7  mov     rax, [rax+10h]
0x180087aab  call    _guard_dispatch_icall
0x180087ab0  nop
0x180087ab1  mov     rcx, [rbp+57h+var_50]
0x180087ab5  test    rcx, rcx
0x180087ab8  jz      short loc_180087AC7
0x180087aba  mov     rax, [rcx]
0x180087abd  mov     rax, [rax+10h]
0x180087ac1  call    _guard_dispatch_icall
0x180087ac6  nop
0x180087ac7  mov     rcx, [rbp+57h+var_68]
0x180087acb  test    rcx, rcx
0x180087ace  jz      short loc_180087ADD
0x180087ad0  mov     rax, [rcx]
0x180087ad3  mov     rax, [rax+10h]
0x180087ad7  call    _guard_dispatch_icall
0x180087adc  nop
0x180087add  mov     rcx, [rbp+57h+var_48]
0x180087ae1  test    rcx, rcx
0x180087ae4  jz      short loc_180087AF3
0x180087ae6  mov     rdx, [rcx]
0x180087ae9  mov     rax, [rdx+10h]
0x180087aed  call    _guard_dispatch_icall
0x180087af2  nop
0x180087af3  jmp     short loc_180087B19
0x180087af5  mov     edx, 34h ; '4'
0x180087afa  jmp     short loc_180087B01
0x180087afc  mov     edx, 33h ; '3'; void *
0x180087b01  mov     ebx, 80070057h
0x180087b06  mov     r9d, ebx; char *
  ... truncated ...
```
