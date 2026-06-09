# Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::InitializePropertyData(Windows::Data::Json::IJsonObject *,Windows::Internal::Security::Authentication::TokenBroker::SerializedPropertyType &,bool &)

- ea: `0x18003a250`
- end: `0x18003a5d1`
- name: `?InitializePropertyData@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@CAJPEAUIJsonObject@Json@Data@6@AEAW4SerializedPropertyType@23456@AEA_N@Z`
- size: `897`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *, enum Windows::Internal::Security::Authentication::TokenBroker::SerializedPropertyType *, bool *)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037330`
- `0x180039e90`
- `0x18003a0c0`
- `0x18003a7f0`

## callees

- `0x180004948`
- `0x180004a0c`
- `0x18000bd40`
- `0x18003a250`
- `0x18003e2f0`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003a2bf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003a44c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003a2bf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003a44c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a2a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a432`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a2a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a432`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a32e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a32e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a300`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a37b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a552`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a5a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a300`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a37b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a552`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a5a2`

## string_xrefs

- `0x18003a2e5`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x18003a3cd`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x18003a476`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::InitializePropertyData(
        struct Windows::Data::Json::IJsonObject *a1,
        enum Windows::Internal::Security::Authentication::TokenBroker::SerializedPropertyType *a2,
        bool *a3)
{
  __int64 (__fastcall *v6)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *); // rdi
  int v7; // eax
  unsigned int v8; // edi
  int v10; // edi
  int v11; // r8d
  int v12; // r9d
  int v13; // eax
  unsigned int v14; // esi
  __int64 v15; // rcx
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, HSTRING, _QWORD, _BYTE *); // r12
  int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rcx
  char v23; // al
  __int64 v24; // rcx
  __int64 v25; // rcx
  int v26; // [rsp+20h] [rbp-59h]
  _BYTE v27[8]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v28; // [rsp+48h] [rbp-31h] BYREF
  HSTRING v29; // [rsp+50h] [rbp-29h] BYREF
  int v30; // [rsp+58h] [rbp-21h] BYREF
  PCWSTR StringRawBuffer; // [rsp+60h] [rbp-19h] BYREF
  _QWORD v32[2]; // [rsp+68h] [rbp-11h] BYREF
  HSTRING string; // [rsp+78h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v29 = 0;
  v6 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *))(*(_QWORD *)a1 + 80LL);
  if ( WindowsCreateStringReference(L"Type", 4u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v7 = v6(a1, string, &v29);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18A,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
      (const char *)(unsigned int)v7,
      v26);
    if ( v29 )
      WindowsDeleteString(v29);
    return v8;
  }
  v10 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::ConvertStringTypeToType(&v29);
  if ( v10 == 5 )
  {
    if ( (unsigned int)dword_180175000 > 2 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(v29, 0);
      v32[0] = "The property type is unknown";
      v30 = -2147023092;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (unsigned int)&v30,
        (unsigned int)byte_18015A2F9,
        v11,
        v12,
        (__int64)&v30,
        (__int64)v32,
        (__int64)&StringRawBuffer);
    }
    if ( v29 )
      WindowsDeleteString(v29);
    return 2147944204LL;
  }
  v27[0] = 0;
  v32[1] = a1;
  (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)a1 + 8LL))(a1);
  v28 = 0;
  v13 = (**(__int64 (__fastcall ***)(struct Windows::Data::Json::IJsonObject *, GUID *, __int64 *))a1)(
          a1,
          &GUID_d960d2a2_b7f0_4f00_8e44_d82cf415ea13,
          &v28);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19C,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
      (const char *)(unsigned int)v13,
      v26);
    v15 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)a1 + 16LL))(a1);
    goto LABEL_35;
  }
  v16 = v28;
  v17 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD, _BYTE *))(*(_QWORD *)v28 + 88LL);
  if ( WindowsCreateStringReference(L"IsProtected", 0xBu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v18 = v17(v16, string, v27[0], v27);
  v14 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
      (const char *)(unsigned int)v18,
      v26);
    v22 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
LABEL_34:
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)a1 + 16LL))(a1);
LABEL_35:
    if ( v29 )
      WindowsDeleteString(v29);
    return v14;
  }
  v23 = v27[0];
  if ( !v27[0] || v10 == 2 )
  {
    *(_DWORD *)a2 = v10;
    *a3 = v23 != 0;
    v25 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    goto LABEL_34;
  }
  if ( (unsigned int)dword_180175000 > 3 )
  {
    v30 = *(_DWORD *)a2;
    v32[0] = "Can't initialize a PROTECTED property with this type";
    LODWORD(StringRawBuffer) = -2147024883;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v19,
      (unsigned int)&word_18015A45E,
      v20,
      v21,
      (__int64)&StringRawBuffer,
      (__int64)v32,
      (__int64)&v30);
  }
  v24 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( v29 )
    WindowsDeleteString(v29);
  return 2147942413LL;
}

```

## disassembly

```asm
0x18003a250  mov     [rsp-8+arg_18], rbx
0x18003a255  push    rbp
0x18003a256  push    rsi
0x18003a257  push    rdi
0x18003a258  push    r12
0x18003a25a  push    r13
0x18003a25c  push    r14
0x18003a25e  push    r15
0x18003a260  lea     rbp, [rsp-27h]
0x18003a265  sub     rsp, 0A0h
0x18003a26c  mov     rax, cs:__security_cookie
0x18003a273  xor     rax, rsp
0x18003a276  mov     [rbp+57h+var_38], rax
0x18003a27a  mov     r13, r8
0x18003a27d  mov     r14, rdx
0x18003a280  mov     rbx, rcx
0x18003a283  xor     r15d, r15d
0x18003a286  mov     [rbp+57h+var_80], r15
0x18003a28a  mov     rax, [rcx]
0x18003a28d  mov     rdi, [rax+50h]
0x18003a291  lea     r9, [rbp+57h+string]; string
0x18003a295  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003a299  mov     edx, 4; length
0x18003a29e  lea     rcx, aType; "Type"
0x18003a2a5  call    cs:__imp_WindowsCreateStringReference
0x18003a2ab  test    eax, eax
0x18003a2ad  jns     short loc_18003A2C5
0x18003a2af  xor     r9d, r9d; lpArguments
0x18003a2b2  xor     r8d, r8d; nNumberOfArguments
0x18003a2b5  mov     edx, 1; dwExceptionFlags
0x18003a2ba  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003a2bf  call    cs:__imp_RaiseException
0x18003a2c5  lea     r8, [rbp+57h+var_80]
0x18003a2c9  mov     rdx, [rbp+57h+string]
0x18003a2cd  mov     rcx, rbx
0x18003a2d0  mov     rax, rdi
0x18003a2d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a2d8  mov     edi, eax
0x18003a2da  test    eax, eax
0x18003a2dc  jns     short loc_18003A30D
0x18003a2de  mov     rcx, [rbp+5Fh]; this
0x18003a2e2  mov     r9d, eax; char *
0x18003a2e5  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18003a2ec  mov     edx, 18Ah; void *
0x18003a2f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a2f6  nop
0x18003a2f7  mov     rcx, [rbp+57h+var_80]; string
0x18003a2fb  test    rcx, rcx
0x18003a2fe  jz      short loc_18003A306
0x18003a300  call    cs:__imp_WindowsDeleteString
0x18003a306  mov     eax, edi
0x18003a308  jmp     loc_18003A5AA
0x18003a30d  lea     rcx, [rbp+57h+var_80]
0x18003a311  call    ?ConvertStringTypeToType@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@CA?AW4SerializedPropertyType@23456@AEBVString@56@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::ConvertStringTypeToType(Windows::Internal::String const &)
0x18003a316  mov     edi, eax
0x18003a318  cmp     eax, 5
0x18003a31b  jnz     short loc_18003A38B
0x18003a31d  mov     eax, cs:dword_180175000
0x18003a323  cmp     eax, 2
0x18003a326  jbe     short loc_18003A372
0x18003a328  xor     edx, edx; length
0x18003a32a  mov     rcx, [rbp+57h+var_80]; string
0x18003a32e  call    cs:__imp_WindowsGetStringRawBuffer
0x18003a334  mov     [rbp+57h+var_70], rax
0x18003a338  lea     rax, aThePropertyTyp; "The property type is unknown"
0x18003a33f  mov     [rbp+57h+var_68], rax
0x18003a343  mov     [rbp+57h+var_78], 8007070Ch
0x18003a34a  lea     rax, [rbp+57h+var_70]
0x18003a34e  mov     [rsp+0D0h+var_A0], rax
0x18003a353  lea     rax, [rbp+57h+var_68]
0x18003a357  mov     [rsp+0D0h+var_A8], rax
0x18003a35c  lea     rcx, [rbp+57h+var_78]
0x18003a360  mov     [rsp+0D0h+var_B0], rcx
0x18003a365  lea     rdx, byte_18015A2F9
0x18003a36c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003a371  nop
0x18003a372  mov     rcx, [rbp+57h+var_80]; string
0x18003a376  test    rcx, rcx
0x18003a379  jz      short loc_18003A381
0x18003a37b  call    cs:__imp_WindowsDeleteString
0x18003a381  mov     eax, 8007070Ch
0x18003a386  jmp     loc_18003A5AA
0x18003a38b  mov     [rbp+57h+var_90], 0
0x18003a38f  mov     [rbp+57h+var_60], rbx
0x18003a393  mov     rax, [rbx]
0x18003a396  mov     rcx, rbx
0x18003a399  mov     rax, [rax+8]
0x18003a39d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3a2  nop
0x18003a3a3  mov     [rbp+57h+var_88], r15
0x18003a3a7  mov     rax, [rbx]
0x18003a3aa  lea     r8, [rbp+57h+var_88]
0x18003a3ae  lea     rdx, _GUID_d960d2a2_b7f0_4f00_8e44_d82cf415ea13
0x18003a3b5  mov     rcx, rbx
0x18003a3b8  mov     rax, [rax]
0x18003a3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3c0  mov     esi, eax
0x18003a3c2  test    eax, eax
0x18003a3c4  jns     short loc_18003A40E
0x18003a3c6  mov     rcx, [rbp+5Fh]; this
0x18003a3ca  mov     r9d, eax; char *
0x18003a3cd  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18003a3d4  mov     edx, 19Ch; void *
0x18003a3d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a3de  nop
0x18003a3df  mov     rcx, [rbp+57h+var_88]
0x18003a3e3  test    rcx, rcx
0x18003a3e6  jz      short loc_18003A3F9
0x18003a3e8  mov     [rbp+57h+var_88], r15
0x18003a3ec  mov     rax, [rcx]
0x18003a3ef  mov     rax, [rax+10h]
0x18003a3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3f8  nop
0x18003a3f9  mov     rax, [rbx]
0x18003a3fc  mov     rcx, rbx
0x18003a3ff  mov     rax, [rax+10h]
0x18003a403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a408  nop
0x18003a409  jmp     loc_18003A599
0x18003a40e  mov     rsi, [rbp+57h+var_88]
0x18003a412  mov     rax, [rsi]
0x18003a415  mov     r12, [rax+58h]
0x18003a419  movzx   r15d, [rbp+57h+var_90]
0x18003a41e  lea     r9, [rbp+57h+string]; string
0x18003a422  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003a426  mov     edx, 0Bh; length
0x18003a42b  lea     rcx, aIsprotected; "IsProtected"
0x18003a432  call    cs:__imp_WindowsCreateStringReference
0x18003a438  test    eax, eax
0x18003a43a  jns     short loc_18003A452
0x18003a43c  xor     r9d, r9d; lpArguments
0x18003a43f  xor     r8d, r8d; nNumberOfArguments
0x18003a442  mov     edx, 1; dwExceptionFlags
0x18003a447  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003a44c  call    cs:__imp_RaiseException
0x18003a452  lea     r9, [rbp+57h+var_90]
0x18003a456  movzx   r8d, r15b
0x18003a45a  mov     rdx, [rbp+57h+string]
0x18003a45e  mov     rcx, rsi
0x18003a461  mov     rax, r12
0x18003a464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a469  mov     esi, eax
0x18003a46b  test    eax, eax
0x18003a46d  jns     short loc_18003A4BB
0x18003a46f  mov     rcx, [rbp+5Fh]; this
0x18003a473  mov     r9d, eax; char *
0x18003a476  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18003a47d  mov     edx, 19Eh; void *
0x18003a482  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a487  nop
0x18003a488  mov     rcx, [rbp+57h+var_88]
0x18003a48c  test    rcx, rcx
0x18003a48f  jz      short loc_18003A4A6
0x18003a491  mov     [rbp+57h+var_88], 0
0x18003a499  mov     rax, [rcx]
0x18003a49c  mov     rax, [rax+10h]
0x18003a4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4a5  nop
0x18003a4a6  mov     rax, [rbx]
0x18003a4a9  mov     rcx, rbx
0x18003a4ac  mov     rax, [rax+10h]
0x18003a4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4b5  nop
0x18003a4b6  jmp     loc_18003A599
0x18003a4bb  movzx   eax, [rbp+57h+var_90]
0x18003a4bf  test    al, al
0x18003a4c1  jz      loc_18003A55F
0x18003a4c7  cmp     edi, 2
0x18003a4ca  jz      loc_18003A55F
0x18003a4d0  mov     eax, cs:dword_180175000
0x18003a4d6  cmp     eax, 3
0x18003a4d9  jbe     short loc_18003A51B
0x18003a4db  mov     eax, [r14]
0x18003a4de  mov     [rbp+57h+var_78], eax
0x18003a4e1  lea     rax, aCanTInitialize; "Can't initialize a PROTECTED property w"...
0x18003a4e8  mov     [rbp+57h+var_68], rax
0x18003a4ec  mov     dword ptr [rbp+57h+var_70], 8007000Dh
0x18003a4f3  lea     rax, [rbp+57h+var_78]
0x18003a4f7  mov     [rsp+0D0h+var_A0], rax
0x18003a4fc  lea     rax, [rbp+57h+var_68]
0x18003a500  mov     [rsp+0D0h+var_A8], rax
0x18003a505  lea     rax, [rbp+57h+var_70]
0x18003a509  mov     [rsp+0D0h+var_B0], rax
0x18003a50e  lea     rdx, word_18015A45E
0x18003a515  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003a51a  nop
0x18003a51b  mov     rcx, [rbp+57h+var_88]
0x18003a51f  test    rcx, rcx
0x18003a522  jz      short loc_18003A539
0x18003a524  mov     [rbp+57h+var_88], 0
0x18003a52c  mov     rax, [rcx]
0x18003a52f  mov     rax, [rax+10h]
0x18003a533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a538  nop
0x18003a539  mov     rax, [rbx]
0x18003a53c  mov     rcx, rbx
0x18003a53f  mov     rax, [rax+10h]
0x18003a543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a548  nop
0x18003a549  mov     rcx, [rbp+57h+var_80]; string
0x18003a54d  test    rcx, rcx
0x18003a550  jz      short loc_18003A558
0x18003a552  call    cs:__imp_WindowsDeleteString
0x18003a558  mov     eax, 8007000Dh
0x18003a55d  jmp     short loc_18003A5AA
0x18003a55f  mov     [r14], edi
0x18003a562  test    al, al
0x18003a564  setnz   al
0x18003a567  mov     [r13+0], al
0x18003a56b  mov     rcx, [rbp+57h+var_88]
0x18003a56f  test    rcx, rcx
0x18003a572  jz      short loc_18003A589
0x18003a574  mov     [rbp+57h+var_88], 0
0x18003a57c  mov     rax, [rcx]
0x18003a57f  mov     rax, [rax+10h]
0x18003a583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a588  nop
0x18003a589  mov     rax, [rbx]
0x18003a58c  mov     rcx, rbx
0x18003a58f  mov     rax, [rax+10h]
0x18003a593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a598  nop
0x18003a599  mov     rcx, [rbp+57h+var_80]; string
0x18003a59d  test    rcx, rcx
0x18003a5a0  jz      short loc_18003A5A8
0x18003a5a2  call    cs:__imp_WindowsDeleteString
0x18003a5a8  mov     eax, esi
0x18003a5aa  mov     rcx, [rbp+57h+var_38]
0x18003a5ae  xor     rcx, rsp; StackCookie
0x18003a5b1  call    __security_check_cookie
0x18003a5b6  mov     rbx, [rsp+0D0h+arg_18]
0x18003a5be  add     rsp, 0A0h
0x18003a5c5  pop     r15
0x18003a5c7  pop     r14
0x18003a5c9  pop     r13
0x18003a5cb  pop     r12
0x18003a5cd  pop     rdi
0x18003a5ce  pop     rsi
0x18003a5cf  pop     rbp
0x18003a5d0  retn
```
