# SetAccountPictureInDataStore(HSTRING__ *,HSTRING__ *,Windows::Storage::Streams::IRandomAccessStream *,HSTRING__ *)

- ea: `0x180073f54`
- end: `0x180074398`
- name: `?SetAccountPictureInDataStore@@YAJPEAUHSTRING__@@0PEAUIRandomAccessStream@Streams@Storage@Windows@@0@Z`
- size: `1092`
- prototype: `int(HSTRING, HSTRING, struct Windows::Storage::Streams::IRandomAccessStream *, HSTRING)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800e32f0`
- `0x1800e3380`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18000fcf8`
- `0x1800286a4`
- `0x180040cc0`
- `0x1800412e0`
- `0x180043370`
- `0x18004c014`
- `0x18004fdbc`
- `0x180073f54`
- `0x180074978`
- `0x180074b84`
- `0x18007c240`
- `0x18007dca4`
- `0x18008e690`
- `0x18009a4c4`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074213`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074254`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074213`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074254`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074319`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007429c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007429c`

## string_xrefs

- `0x180073fcb`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180073ffb`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18007405b`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180074094`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x1800740e2`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180074120`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180074171`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x1800741b6`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x1800741f8`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180074239`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SetAccountPictureInDataStore(
        HSTRING a1,
        HSTRING a2,
        struct Windows::Storage::Streams::IRandomAccessStream *a3,
        HSTRING a4)
{
  int v8; // eax
  bool v9; // r8
  unsigned int v10; // edi
  int updated; // eax
  unsigned int v13; // esi
  unsigned __int64 *v14; // rdx
  int CurrentUserContext; // eax
  unsigned int v16; // ebx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64, __int64 *); // rbx
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64 *); // rbx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rax
  int v29; // [rsp+20h] [rbp-69h]
  int v30; // [rsp+20h] [rbp-69h]
  __int64 v31; // [rsp+30h] [rbp-59h] BYREF
  __int64 v32; // [rsp+38h] [rbp-51h] BYREF
  __int64 v33; // [rsp+40h] [rbp-49h] BYREF
  __int64 v34; // [rsp+48h] [rbp-41h] BYREF
  HSTRING string; // [rsp+50h] [rbp-39h] BYREF
  HSTRING v36; // [rsp+58h] [rbp-31h] BYREF
  HSTRING v37; // [rsp+60h] [rbp-29h] BYREF
  __int64 v38; // [rsp+68h] [rbp-21h] BYREF
  __int64 v39; // [rsp+70h] [rbp-19h] BYREF
  __int64 v40; // [rsp+78h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-9h] BYREF
  __int64 v42; // [rsp+98h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v36 = a1;
  if ( (unsigned int)dword_180175000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      byte_1801584A3,
      0,
      0);
  v8 = WriteAccountPictureData(a1, a2, a3);
  v10 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB11,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v8,
      v29);
    return v10;
  }
  updated = UpdateAccountRevisionNumber(a1, a2, v9);
  v13 = updated;
  if ( updated < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB1A,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)updated,
      v29);
    return v13;
  }
  TrySignalAccountEvent(5, a1, a2, 0, 0);
  TrySignalAccountEvent(6, a1, a2, 0, a4);
  v39 = 0;
  CurrentUserContext = Windows::Internal::Security::Authentication::TokenBroker::GetCurrentUserContext(
                         (Windows::Internal::Security::Authentication::TokenBroker *)&v39,
                         v14);
  v16 = CurrentUserContext;
  if ( CurrentUserContext >= 0 )
  {
    v38 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    v17 = Windows::Internal::Security::Authentication::TokenBroker::CreateTokenBrokerInternalStaticsT<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics5>(&v38);
    v16 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB29,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v17,
        v30);
LABEL_43:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      return v16;
    }
    v31 = 0;
    v18 = v38;
    v19 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v38 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    v20 = v19(v18, v39, &v31);
    v16 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB2C,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v20,
        v30);
LABEL_13:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      goto LABEL_43;
    }
    v33 = 0;
    v21 = BlockOnCompletionAndGetResults<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *,Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult>(
            v31,
            &v33);
    v16 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB2F,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v21,
        v30);
LABEL_16:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      goto LABEL_13;
    }
    v32 = 0;
    v22 = v33;
    v23 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    v24 = v23(v22, &v32);
    v16 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB32,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v24,
        v30);
LABEL_19:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      goto LABEL_16;
    }
    if ( v32 )
    {
      v34 = 0;
      v25 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
              &v32,
              &v34);
      v16 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB37,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
          (const char *)(unsigned int)v25,
          v30);
LABEL_23:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
        goto LABEL_19;
      }
      string = 0;
      v26 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v34 + 48LL))(v34, &string);
      v16 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB3A,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
          (const char *)(unsigned int)v26,
          v30);
LABEL_26:
        if ( string )
          WindowsDeleteString(string);
        goto LABEL_23;
      }
      v37 = 0;
      v27 = Windows::Internal::String::Initialize((Windows::Internal::String *)&v37, &v36);
      v16 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB3D,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
          (const char *)(unsigned int)v27,
          v30);
        if ( v37 )
          WindowsDeleteString(v37);
        goto LABEL_26;
      }
      if ( (unsigned int)Windows::Internal::StringReference::CompareOrdinal(
                           (Windows::Internal::StringReference *)&string,
                           (const struct Windows::Internal::String *)&v37) )
      {
        if ( (unsigned int)dword_180175000 > 4 )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_180175000,
            &dword_1801585D4,
            0,
            0);
      }
      else
      {
        v36 = 0;
        v42 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.System.Internal.UserManager",
          0x24u,
          0x23u);
        RoGetActivationFactory(v42, &GUID_e3ef19ae_1599_4fc8_beb1_6616f62ad07a, &v36);
        v40 = 0;
        v28 = *(_QWORD *)v36;
        v40 = 0;
        (*(void (__fastcall **)(HSTRING, __int64, HSTRING, __int64 *))(v28 + 64))(v36, v39, a4, &v40);
        wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v40);
        wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v36);
      }
      if ( v37 )
        WindowsDeleteString(v37);
      if ( string )
        WindowsDeleteString(string);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    }
    else if ( (unsigned int)dword_180175000 > 4 )
    {
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_180175000,
        word_180158592,
        0,
        0);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    v16 = v13;
    goto LABEL_43;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB26,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
    (const char *)(unsigned int)CurrentUserContext,
    v30);
  return v16;
}

```

## disassembly

```asm
0x180073f54  push    rbp
0x180073f56  push    rbx
0x180073f57  push    rsi
0x180073f58  push    rdi
0x180073f59  push    r12
0x180073f5b  push    r14
0x180073f5d  push    r15
0x180073f5f  lea     rbp, [rsp-27h]
0x180073f64  sub     rsp, 0B0h
0x180073f6b  mov     rax, cs:__security_cookie
0x180073f72  xor     rax, rsp
0x180073f75  mov     [rbp+57h+var_40], rax
0x180073f79  mov     r15, r9
0x180073f7c  mov     rdi, r8
0x180073f7f  mov     r14, rdx
0x180073f82  mov     rbx, rcx
0x180073f85  mov     [rbp+57h+var_88], rcx
0x180073f89  mov     eax, cs:dword_180175000
0x180073f8f  cmp     eax, 4
0x180073f92  jbe     short loc_180073FAD
0x180073f94  xor     r9d, r9d
0x180073f97  xor     r8d, r8d
0x180073f9a  lea     rdx, byte_1801584A3
0x180073fa1  lea     rcx, dword_180175000
0x180073fa8  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180073fad  mov     r8, rdi; struct Windows::Storage::Streams::IRandomAccessStream *
0x180073fb0  mov     rdx, r14; HSTRING
0x180073fb3  mov     rcx, rbx; HSTRING
0x180073fb6  call    ?WriteAccountPictureData@@YAJPEAUHSTRING__@@0PEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; WriteAccountPictureData(HSTRING__ *,HSTRING__ *,Windows::Storage::Streams::IRandomAccessStream *)
0x180073fbb  mov     edi, eax
0x180073fbd  xor     r12d, r12d
0x180073fc0  test    eax, eax
0x180073fc2  jns     short loc_180073FE3
0x180073fc4  mov     rcx, [rbp+5Fh]; this
0x180073fc8  mov     r9d, eax; char *
0x180073fcb  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180073fd2  mov     edx, 0B11h; void *
0x180073fd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073fdc  mov     eax, edi
0x180073fde  jmp     loc_18007437A
0x180073fe3  mov     rdx, r14; HSTRING
0x180073fe6  mov     rcx, rbx; string
0x180073fe9  call    ?UpdateAccountRevisionNumber@@YAJPEAUHSTRING__@@0_N@Z; UpdateAccountRevisionNumber(HSTRING__ *,HSTRING__ *,bool)
0x180073fee  mov     esi, eax
0x180073ff0  test    eax, eax
0x180073ff2  jns     short loc_180074013
0x180073ff4  mov     rcx, [rbp+5Fh]; this
0x180073ff8  mov     r9d, eax; char *
0x180073ffb  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180074002  mov     edx, 0B1Ah; void *
0x180074007  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007400c  mov     eax, esi
0x18007400e  jmp     loc_18007437A
0x180074013  mov     qword ptr [rsp+0E0h+var_C0], r12
0x180074018  xor     r9d, r9d
0x18007401b  mov     r8, r14
0x18007401e  mov     rdx, rbx
0x180074021  lea     ecx, [r9+5]
0x180074025  call    ?TrySignalAccountEvent@@YAXW4SystemEventType@Web@Authentication@Security@Internal@Windows@@PEAUHSTRING__@@1PEAUIWebAccountProvider@Credentials@46@1@Z; TrySignalAccountEvent(Windows::Internal::Security::Authentication::Web::SystemEventType,HSTRING__ *,HSTRING__ *,Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ *)
0x18007402a  mov     qword ptr [rsp+0E0h+var_C0], r15; int
0x18007402f  xor     r9d, r9d
0x180074032  mov     r8, r14
0x180074035  mov     rdx, rbx
0x180074038  lea     ecx, [r9+6]
0x18007403c  call    ?TrySignalAccountEvent@@YAXW4SystemEventType@Web@Authentication@Security@Internal@Windows@@PEAUHSTRING__@@1PEAUIWebAccountProvider@Credentials@46@1@Z; TrySignalAccountEvent(Windows::Internal::Security::Authentication::Web::SystemEventType,HSTRING__ *,HSTRING__ *,Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ *)
0x180074041  mov     [rbp+57h+var_70], r12
0x180074045  lea     rcx, [rbp+57h+var_70]; this
0x180074049  call    ?GetCurrentUserContext@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEA_K@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCurrentUserContext(unsigned __int64 *)
0x18007404e  mov     ebx, eax
0x180074050  test    eax, eax
0x180074052  jns     short loc_180074071
0x180074054  mov     rcx, [rbp+5Fh]; this
0x180074058  mov     r9d, eax; char *
0x18007405b  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180074062  mov     edx, 0B26h; void *
0x180074067  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007406c  jmp     loc_180074378
0x180074071  mov     [rbp+57h+var_78], r12
0x180074075  lea     rcx, [rbp+57h+var_78]
0x180074079  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007407e  lea     rcx, [rbp+57h+var_78]
0x180074082  call    ??$CreateTokenBrokerInternalStaticsT@UITokenBrokerInternalStatics5@Web@Authentication@Security@Internal@Windows@@@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAPEAUITokenBrokerInternalStatics5@Web@1234@@Z; Windows::Internal::Security::Authentication::TokenBroker::CreateTokenBrokerInternalStaticsT<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics5>(Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics5 * *)
0x180074087  mov     ebx, eax
0x180074089  test    eax, eax
0x18007408b  jns     short loc_1800740AA
0x18007408d  mov     rcx, [rbp+5Fh]; this
0x180074091  mov     r9d, eax; char *
0x180074094  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18007409b  mov     edx, 0B29h; void *
0x1800740a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800740a5  jmp     loc_18007436F
0x1800740aa  mov     [rbp+57h+var_B0], r12
0x1800740ae  mov     rdi, [rbp+57h+var_78]
0x1800740b2  mov     rax, [rdi]
0x1800740b5  mov     rbx, [rax+38h]
0x1800740b9  lea     rcx, [rbp+57h+var_B0]
0x1800740bd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800740c2  lea     r8, [rbp+57h+var_B0]
0x1800740c6  mov     rdx, [rbp+57h+var_70]
0x1800740ca  mov     rcx, rdi
0x1800740cd  mov     rax, rbx
0x1800740d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800740d5  mov     ebx, eax
0x1800740d7  test    eax, eax
0x1800740d9  jns     short loc_180074102
0x1800740db  mov     rcx, [rbp+5Fh]; this
0x1800740df  mov     r9d, eax; char *
0x1800740e2  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800740e9  mov     edx, 0B2Ch; void *
0x1800740ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800740f3  nop
0x1800740f4  lea     rcx, [rbp+57h+var_B0]
0x1800740f8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800740fd  jmp     loc_18007436F
0x180074102  mov     [rbp+57h+var_A0], r12
0x180074106  lea     rdx, [rbp+57h+var_A0]
0x18007410a  mov     rcx, [rbp+57h+var_B0]
0x18007410e  call    ??$BlockOnCompletionAndGetResults@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@UIGetDefaultSignInAccountResult@23456@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *,Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult>>,tagCOWAIT_FLAGS,void *)
0x180074113  mov     ebx, eax
0x180074115  test    eax, eax
0x180074117  jns     short loc_18007413D
0x180074119  mov     rcx, [rbp+5Fh]; this
0x18007411d  mov     r9d, eax; char *
0x180074120  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180074127  mov     edx, 0B2Fh; void *
0x18007412c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074131  nop
0x180074132  lea     rcx, [rbp+57h+var_A0]
0x180074136  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007413b  jmp     short loc_1800740F4
0x18007413d  mov     [rbp+57h+var_A8], r12
0x180074141  mov     rdi, [rbp+57h+var_A0]
0x180074145  mov     rax, [rdi]
0x180074148  mov     rbx, [rax+30h]
0x18007414c  lea     rcx, [rbp+57h+var_A8]
0x180074150  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180074155  lea     rdx, [rbp+57h+var_A8]
0x180074159  mov     rcx, rdi
0x18007415c  mov     rax, rbx
0x18007415f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074164  mov     ebx, eax
0x180074166  test    eax, eax
0x180074168  jns     short loc_18007418E
0x18007416a  mov     rcx, [rbp+5Fh]; this
0x18007416e  mov     r9d, eax; char *
0x180074171  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180074178  mov     edx, 0B32h; void *
0x18007417d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074182  nop
0x180074183  lea     rcx, [rbp+57h+var_A8]
0x180074187  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007418c  jmp     short loc_180074132
0x18007418e  cmp     [rbp+57h+var_A8], r12
0x180074192  jz      loc_18007432B
0x180074198  mov     [rbp+57h+var_98], r12
0x18007419c  lea     rdx, [rbp+57h+var_98]
0x1800741a0  lea     rcx, [rbp+57h+var_A8]
0x1800741a4  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x1800741a9  mov     ebx, eax
0x1800741ab  test    eax, eax
0x1800741ad  jns     short loc_1800741D3
0x1800741af  mov     rcx, [rbp+5Fh]; this
0x1800741b3  mov     r9d, eax; char *
0x1800741b6  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800741bd  mov     edx, 0B37h; void *
0x1800741c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800741c7  nop
0x1800741c8  lea     rcx, [rbp+57h+var_98]
0x1800741cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800741d1  jmp     short loc_180074183
0x1800741d3  mov     [rbp+57h+string], r12
0x1800741d7  mov     rcx, [rbp+57h+var_98]
0x1800741db  mov     rax, [rcx]
0x1800741de  lea     rdx, [rbp+57h+string]
0x1800741e2  mov     rax, [rax+30h]
0x1800741e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800741eb  mov     ebx, eax
0x1800741ed  test    eax, eax
0x1800741ef  jns     short loc_18007421B
0x1800741f1  mov     rcx, [rbp+5Fh]; this
0x1800741f5  mov     r9d, eax; char *
0x1800741f8  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800741ff  mov     edx, 0B3Ah; void *
0x180074204  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074209  nop
0x18007420a  mov     rcx, [rbp+57h+string]; string
0x18007420e  test    rcx, rcx
0x180074211  jz      short loc_1800741C8
0x180074213  call    cs:__imp_WindowsDeleteString
0x180074219  jmp     short loc_1800741C8
0x18007421b  mov     [rbp+57h+var_80], r12
0x18007421f  lea     rdx, [rbp+57h+var_88]; HSTRING *
0x180074223  lea     rcx, [rbp+57h+var_80]; this
0x180074227  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x18007422c  mov     ebx, eax
0x18007422e  test    eax, eax
0x180074230  jns     short loc_18007425C
0x180074232  mov     rcx, [rbp+5Fh]; this
0x180074236  mov     r9d, eax; char *
0x180074239  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180074240  mov     edx, 0B3Dh; void *
0x180074245  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007424a  nop
0x18007424b  mov     rcx, [rbp+57h+var_80]; string
0x18007424f  test    rcx, rcx
0x180074252  jz      short loc_18007420A
0x180074254  call    cs:__imp_WindowsDeleteString
0x18007425a  jmp     short loc_18007420A
0x18007425c  lea     rdx, [rbp+57h+var_80]; struct Windows::Internal::String *
0x180074260  lea     rcx, [rbp+57h+string]; this
0x180074264  call    ?CompareOrdinal@StringReference@Internal@Windows@@QEBAHAEBVString@23@@Z; Windows::Internal::StringReference::CompareOrdinal(Windows::Internal::String const &)
0x180074269  test    eax, eax
0x18007426b  jnz     short loc_1800742DB
0x18007426d  mov     [rbp+57h+var_88], r12
0x180074271  mov     [rbp+57h+var_48], r12
0x180074275  lea     r9d, [rax+23h]; unsigned int
0x180074279  lea     r8d, [rax+24h]; unsigned int
0x18007427d  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180074284  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180074288  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007428d  lea     r8, [rbp+57h+var_88]
0x180074291  lea     rdx, _GUID_e3ef19ae_1599_4fc8_beb1_6616f62ad07a
0x180074298  mov     rcx, [rbp+57h+var_48]
0x18007429c  call    cs:__imp_RoGetActivationFactory
0x1800742a2  mov     [rbp+57h+var_68], r12
0x1800742a6  mov     rcx, [rbp+57h+var_88]
0x1800742aa  mov     rax, [rcx]
0x1800742ad  mov     [rbp+57h+var_68], r12
0x1800742b1  lea     r9, [rbp+57h+var_68]
0x1800742b5  mov     r8, r15
0x1800742b8  mov     rdx, [rbp+57h+var_70]
0x1800742bc  mov     rax, [rax+40h]
0x1800742c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800742c5  nop
0x1800742c6  lea     rcx, [rbp+57h+var_68]
0x1800742ca  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x1800742cf  nop
0x1800742d0  lea     rcx, [rbp+57h+var_88]
0x1800742d4  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x1800742d9  jmp     short loc_180074300
0x1800742db  mov     eax, cs:dword_180175000
0x1800742e1  cmp     eax, 4
0x1800742e4  jbe     short loc_180074300
0x1800742e6  xor     r9d, r9d
0x1800742e9  xor     r8d, r8d
0x1800742ec  lea     rdx, dword_1801585D4
0x1800742f3  lea     rcx, dword_180175000
0x1800742fa  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800742ff  nop
0x180074300  mov     rcx, [rbp+57h+var_80]; string
0x180074304  test    rcx, rcx
0x180074307  jz      short loc_180074310
0x180074309  call    cs:__imp_WindowsDeleteString
0x18007430f  nop
0x180074310  mov     rcx, [rbp+57h+string]; string
0x180074314  test    rcx, rcx
0x180074317  jz      short loc_180074320
0x180074319  call    cs:__imp_WindowsDeleteString
0x18007431f  nop
0x180074320  lea     rcx, [rbp+57h+var_98]
0x180074324  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180074329  jmp     short loc_180074350
0x18007432b  mov     eax, cs:dword_180175000
0x180074331  cmp     eax, 4
0x180074334  jbe     short loc_180074350
0x180074336  xor     r9d, r9d
0x180074339  xor     r8d, r8d
0x18007433c  lea     rdx, word_180158592
0x180074343  lea     rcx, dword_180175000
0x18007434a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007434f  nop
0x180074350  lea     rcx, [rbp+57h+var_A8]
0x180074354  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180074359  nop
0x18007435a  lea     rcx, [rbp+57h+var_A0]
0x18007435e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180074363  nop
0x180074364  lea     rcx, [rbp+57h+var_B0]
0x180074368  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007436d  mov     ebx, esi
0x18007436f  lea     rcx, [rbp+57h+var_78]
0x180074373  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180074378  mov     eax, ebx
0x18007437a  mov     rcx, [rbp+57h+var_40]
0x18007437e  xor     rcx, rsp; StackCookie
0x180074381  call    __security_check_cookie
0x180074386  add     rsp, 0B0h
0x18007438d  pop     r15
0x18007438f  pop     r14
0x180074391  pop     r12
0x180074393  pop     rdi
0x180074394  pop     rsi
0x180074395  pop     rbx
0x180074396  pop     rbp
0x180074397  retn
```
