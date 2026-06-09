# Windows::Internal::Security::Authentication::TokenBroker::JsonObjectHeader::Initialize(Windows::Data::Json::IJsonObject *)

- ea: `0x1800792b0`
- end: `0x180079541`
- name: `?Initialize@JsonObjectHeader@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAUIJsonObject@Json@Data@6@@Z`
- size: `657`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::TokenBroker::JsonObjectHeader *__hidden this, struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b540`

## callees

- `0x180004a0c`
- `0x18000bd40`
- `0x180044e2c`
- `0x180053500`
- `0x1800792b0`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180079315`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800793d9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007945b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180079315`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800793d9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007945b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800792fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800793bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180079441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800792fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800793bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180079441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800794e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800794e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007949c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079531`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007949c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079531`

## string_xrefs

- `0x18007933b`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x1800793ff`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x180079481`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::JsonObjectHeader::Initialize(
        Windows::Internal::Security::Authentication::TokenBroker::JsonObjectHeader *this,
        struct Windows::Data::Json::IJsonObject *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Data::Json::IJsonObject *, HSTRING, double *); // rbx
  int v5; // eax
  int v6; // r8d
  int v7; // r9d
  unsigned int v8; // ebx
  unsigned int v9; // eax
  __int64 (__fastcall *v11)(struct Windows::Data::Json::IJsonObject *, HSTRING, double *); // rbx
  int v12; // eax
  __int64 (__fastcall *v13)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *); // rbx
  int v14; // eax
  int v15; // eax
  int v16; // r8d
  int v17; // r9d
  int v18; // [rsp+20h] [rbp-29h]
  int v19; // [rsp+40h] [rbp-9h] BYREF
  HSTRING v20; // [rsp+48h] [rbp-1h] BYREF
  double v21; // [rsp+50h] [rbp+7h] BYREF
  PCWSTR StringRawBuffer; // [rsp+58h] [rbp+Fh] BYREF
  const char *v23; // [rsp+60h] [rbp+17h] BYREF
  HSTRING string; // [rsp+68h] [rbp+1Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v21 = 0.0;
  v4 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, double *))(*(_QWORD *)a2 + 88LL);
  if ( WindowsCreateStringReference(L"SchemaVersionMajor", 0x12u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v5 = v4(a2, string, &v21);
  v8 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
      (const char *)(unsigned int)v5,
      v18);
    return v8;
  }
  v9 = (int)v21;
  *((_DWORD *)this + 1) = (int)v21;
  if ( v9 > 2 )
  {
    if ( (unsigned int)dword_180175000 > 2 )
    {
      StringRawBuffer = (PCWSTR)"The major schema of the object is too high";
      v19 = -2147024883;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)&v19,
        (unsigned int)byte_18015A4B3,
        v6,
        v7,
        (__int64)&v19,
        (__int64)&StringRawBuffer);
    }
    return 2147942413LL;
  }
  v11 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, double *))(*(_QWORD *)a2 + 88LL);
  if ( WindowsCreateStringReference(L"SchemaVersionMinor", 0x12u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v12 = v11(a2, string, &v21);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
      (const char *)(unsigned int)v12,
      v18);
    return v8;
  }
  *((_DWORD *)this + 2) = (int)v21;
  v20 = 0;
  v13 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *))(*(_QWORD *)a2 + 80LL);
  if ( WindowsCreateStringReference(L"ObjectType", 0xAu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v14 = v13(a2, string, &v20);
  v8 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
      (const char *)(unsigned int)v14,
      v18);
    goto LABEL_17;
  }
  v15 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectHeader::ConvertStringTypeToType(&v20);
  *(_DWORD *)this = v15;
  if ( v15 != 5 )
  {
LABEL_17:
    if ( v20 )
      WindowsDeleteString(v20);
    return v8;
  }
  if ( (unsigned int)dword_180175000 > 2 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v20, 0);
    v23 = "The object type is unknown";
    v19 = -2147023092;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      (unsigned int)&v19,
      (unsigned int)byte_18015A4F1,
      v16,
      v17,
      (__int64)&v19,
      (__int64)&v23,
      (__int64)&StringRawBuffer);
  }
  if ( v20 )
    WindowsDeleteString(v20);
  return 2147944204LL;
}

```

## disassembly

```asm
0x1800792b0  mov     [rsp-8+arg_10], rbx
0x1800792b5  push    rbp
0x1800792b6  push    rsi
0x1800792b7  push    rdi
0x1800792b8  lea     rbp, [rsp-47h]
0x1800792bd  sub     rsp, 90h
0x1800792c4  mov     rax, cs:__security_cookie
0x1800792cb  xor     rax, rsp
0x1800792ce  mov     [rbp+57h+var_18], rax
0x1800792d2  mov     rdi, rdx
0x1800792d5  mov     rsi, rcx
0x1800792d8  xorps   xmm0, xmm0
0x1800792db  movsd   [rbp+57h+var_50], xmm0
0x1800792e0  mov     rax, [rdx]
0x1800792e3  mov     rbx, [rax+58h]
0x1800792e7  lea     r9, [rbp+57h+string]; string
0x1800792eb  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800792ef  mov     edx, 12h; length
0x1800792f4  lea     rcx, aSchemaversionm_0; "SchemaVersionMajor"
0x1800792fb  call    cs:__imp_WindowsCreateStringReference
0x180079301  test    eax, eax
0x180079303  jns     short loc_18007931B
0x180079305  xor     r9d, r9d; lpArguments
0x180079308  xor     r8d, r8d; nNumberOfArguments
0x18007930b  mov     edx, 1; dwExceptionFlags
0x180079310  mov     ecx, 0C000000Dh; dwExceptionCode
0x180079315  call    cs:__imp_RaiseException
0x18007931b  lea     r8, [rbp+57h+var_50]
0x18007931f  mov     rdx, [rbp+57h+string]
0x180079323  mov     rcx, rdi
0x180079326  mov     rax, rbx
0x180079329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007932e  mov     ebx, eax
0x180079330  test    eax, eax
0x180079332  jns     short loc_180079351
0x180079334  mov     rcx, [rbp+5Fh]; this
0x180079338  mov     r9d, eax; char *
0x18007933b  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180079342  mov     edx, 51h ; 'Q'; void *
0x180079347  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007934c  jmp     loc_1800794A2
0x180079351  cvttsd2si rax, [rbp+57h+var_50]
0x180079357  mov     [rsi+4], eax
0x18007935a  cmp     eax, 2
0x18007935d  jbe     short loc_1800793A4
0x18007935f  mov     eax, cs:dword_180175000
0x180079365  cmp     eax, 2
0x180079368  jbe     short loc_18007939A
0x18007936a  lea     rcx, aTheMajorSchema; "The major schema of the object is too h"...
0x180079371  mov     [rbp+57h+var_48], rcx
0x180079375  mov     [rbp+57h+var_60], 8007000Dh
0x18007937c  lea     rcx, [rbp+57h+var_48]
0x180079380  mov     [rsp+0A0h+var_78], rcx
0x180079385  lea     rcx, [rbp+57h+var_60]
0x180079389  mov     [rsp+0A0h+var_80], rcx
0x18007938e  lea     rdx, byte_18015A4B3
0x180079395  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18007939a  mov     eax, 8007000Dh
0x18007939f  jmp     loc_1800794A4
0x1800793a4  mov     rax, [rdi]
0x1800793a7  mov     rbx, [rax+58h]
0x1800793ab  lea     r9, [rbp+57h+string]; string
0x1800793af  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800793b3  mov     edx, 12h; length
0x1800793b8  lea     rcx, aSchemaversionm; "SchemaVersionMinor"
0x1800793bf  call    cs:__imp_WindowsCreateStringReference
0x1800793c5  test    eax, eax
0x1800793c7  jns     short loc_1800793DF
0x1800793c9  xor     r9d, r9d; lpArguments
0x1800793cc  xor     r8d, r8d; nNumberOfArguments
0x1800793cf  mov     edx, 1; dwExceptionFlags
0x1800793d4  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800793d9  call    cs:__imp_RaiseException
0x1800793df  lea     r8, [rbp+57h+var_50]
0x1800793e3  mov     rdx, [rbp+57h+string]
0x1800793e7  mov     rcx, rdi
0x1800793ea  mov     rax, rbx
0x1800793ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800793f2  mov     ebx, eax
0x1800793f4  test    eax, eax
0x1800793f6  jns     short loc_180079415
0x1800793f8  mov     rcx, [rbp+5Fh]; this
0x1800793fc  mov     r9d, eax; char *
0x1800793ff  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180079406  mov     edx, 60h ; '`'; void *
0x18007940b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079410  jmp     loc_1800794A2
0x180079415  cvttsd2si rax, [rbp+57h+var_50]
0x18007941b  mov     [rsi+8], eax
0x18007941e  mov     [rbp+57h+var_58], 0
0x180079426  mov     rax, [rdi]
0x180079429  mov     rbx, [rax+50h]
0x18007942d  lea     r9, [rbp+57h+string]; string
0x180079431  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180079435  mov     edx, 0Ah; length
0x18007943a  lea     rcx, aObjecttype; "ObjectType"
0x180079441  call    cs:__imp_WindowsCreateStringReference
0x180079447  test    eax, eax
0x180079449  jns     short loc_180079461
0x18007944b  xor     r9d, r9d; lpArguments
0x18007944e  xor     r8d, r8d; nNumberOfArguments
0x180079451  mov     edx, 1; dwExceptionFlags
0x180079456  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007945b  call    cs:__imp_RaiseException
0x180079461  lea     r8, [rbp+57h+var_58]
0x180079465  mov     rdx, [rbp+57h+string]
0x180079469  mov     rcx, rdi
0x18007946c  mov     rax, rbx
0x18007946f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079474  mov     ebx, eax
0x180079476  test    eax, eax
0x180079478  jns     short loc_1800794C3
0x18007947a  mov     rcx, [rbp+5Fh]; this
0x18007947e  mov     r9d, eax; char *
0x180079481  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180079488  mov     edx, 65h ; 'e'; void *
0x18007948d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079492  nop
0x180079493  mov     rcx, [rbp+57h+var_58]; string
0x180079497  test    rcx, rcx
0x18007949a  jz      short loc_1800794A2
0x18007949c  call    cs:__imp_WindowsDeleteString
0x1800794a2  mov     eax, ebx
0x1800794a4  mov     rcx, [rbp+57h+var_18]
0x1800794a8  xor     rcx, rsp; StackCookie
0x1800794ab  call    __security_check_cookie
0x1800794b0  mov     rbx, [rsp+0A0h+arg_10]
0x1800794b8  add     rsp, 90h
0x1800794bf  pop     rdi
0x1800794c0  pop     rsi
0x1800794c1  pop     rbp
0x1800794c2  retn
0x1800794c3  lea     rcx, [rbp+57h+var_58]
0x1800794c7  call    ?ConvertStringTypeToType@JsonObjectHeader@TokenBroker@Authentication@Security@Internal@Windows@@SA?AW4SerializedObjectType@23456@AEBVString@56@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectHeader::ConvertStringTypeToType(Windows::Internal::String const &)
0x1800794cc  mov     [rsi], eax
0x1800794ce  cmp     eax, 5
0x1800794d1  jnz     short loc_180079493
0x1800794d3  mov     eax, cs:dword_180175000
0x1800794d9  cmp     eax, 2
0x1800794dc  jbe     short loc_180079528
0x1800794de  xor     edx, edx; length
0x1800794e0  mov     rcx, [rbp+57h+var_58]; string
0x1800794e4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800794ea  mov     [rbp+57h+var_48], rax
0x1800794ee  lea     rax, aTheObjectTypeI; "The object type is unknown"
0x1800794f5  mov     [rbp+57h+var_40], rax
0x1800794f9  mov     [rbp+57h+var_60], 8007070Ch
0x180079500  lea     rax, [rbp+57h+var_48]
0x180079504  mov     [rsp+0A0h+var_70], rax
0x180079509  lea     rax, [rbp+57h+var_40]
0x18007950d  mov     [rsp+0A0h+var_78], rax
0x180079512  lea     rcx, [rbp+57h+var_60]
0x180079516  mov     [rsp+0A0h+var_80], rcx
0x18007951b  lea     rdx, byte_18015A4F1
0x180079522  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180079527  nop
0x180079528  mov     rcx, [rbp+57h+var_58]; string
0x18007952c  test    rcx, rcx
0x18007952f  jz      short loc_180079537
0x180079531  call    cs:__imp_WindowsDeleteString
0x180079537  mov     eax, 8007070Ch
0x18007953c  jmp     loc_1800794A4
```
