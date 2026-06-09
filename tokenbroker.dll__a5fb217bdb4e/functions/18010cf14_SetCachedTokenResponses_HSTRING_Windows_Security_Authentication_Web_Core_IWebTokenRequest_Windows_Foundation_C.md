# SetCachedTokenResponses(HSTRING__ *,Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,Windows::Security::Authentication::Web::Core::WebTokenRequestStatus,Windows::Foundation::DateTime,Windows::Storage::Streams::IBuffer *,Windows::Storage::Streams::IBuffer *,Windows::Internal::Security::Authentication::TokenBroker::TB_REQUEST_ID *)

- ea: `0x18010cf14`
- end: `0x18010d6f3`
- name: `?SetCachedTokenResponses@@YAJPEAUHSTRING__@@PEAUIWebTokenRequest@Core@Web@Authentication@Security@Windows@@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@7@W4WebTokenRequestStatus@34567@UDateTime@Foundation@7@PEAUIBuffer@Streams@Storage@7@5PEAUTB_REQUEST_ID@TokenBroker@56Internal@7@@Z`
- size: `2015`
- prototype: `__int64 __usercall@<rax>(HSTRING string2@<rcx>, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ee430`

## callees

- `0x1800050b0`
- `0x180005f00`
- `0x180006048`
- `0x180007350`
- `0x18000bd40`
- `0x180010a70`
- `0x180024544`
- `0x18003ac98`
- `0x180045454`
- `0x1800454f0`
- `0x18004dc68`
- `0x18004e850`
- `0x180053cfc`
- `0x180063a74`
- `0x180070660`
- `0x18007f6e0`
- `0x180109c80`
- `0x180109dd8`
- `0x18010aff4`
- `0x18010bffc`
- `0x18010c210`
- `0x18010c284`
- `0x18010c9e8`
- `0x18010ce0c`
- `0x18010cf14`
- `0x18010d75c`
- `0x18010dc5c`
- `0x18011b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010cfc6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010cfc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010cfb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010d008`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010d017`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010cfb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010d008`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010d017`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010cfa3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010d0bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010d1a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010d218`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010d690`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010cfa3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010d0bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010d1a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010d218`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010d690`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010d3d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010d658`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010d3d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010d658`

## string_xrefs

- `0x18010cf88`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010d1e9`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010d264`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010d2ac`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010d33e`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010d3b4`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010d419`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010d4a2`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010d533`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010d6dc`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SetCachedTokenResponses(
        HSTRING string2,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        HLOCAL *a3,
        int a4,
        const WCHAR *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  int v12; // eax
  unsigned int v13; // ebx
  PCWSTR StringRawBuffer; // rax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // r9d
  __int64 (__fastcall *v26)(_QWORD, GUID *, __int64 *); // rdi
  int v27; // eax
  int v28; // edi
  int AllAccountsFromResponses; // eax
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rsi
  __int64 (__fastcall *v33)(__int64, __int64 *); // rdi
  int v34; // eax
  HLOCAL v35; // rcx
  int v36; // eax
  char v37; // r12
  int v38; // eax
  unsigned int v39; // esi
  HLOCAL v40; // rcx
  __int64 (__fastcall *v41)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v42; // rdx
  bool v43; // dl
  _DWORD *v44; // rbx
  rsize_t v45; // rdx
  int v46; // eax
  int v47; // [rsp+20h] [rbp-E0h]
  int v48; // [rsp+20h] [rbp-E0h]
  int v49; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+70h] [rbp-90h] BYREF
  __int64 v51; // [rsp+78h] [rbp-88h] BYREF
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  __int64 v53; // [rsp+88h] [rbp-78h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v54; // [rsp+90h] [rbp-70h] BYREF
  __int64 v55; // [rsp+98h] [rbp-68h] BYREF
  rsize_t SourceSize; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v57; // [rsp+A8h] [rbp-58h] BYREF
  char v58[16]; // [rsp+B0h] [rbp-50h] BYREF
  int v59[2]; // [rsp+C0h] [rbp-40h] BYREF
  char v60; // [rsp+C8h] [rbp-38h]
  int v61; // [rsp+C9h] [rbp-37h]
  __int16 v62; // [rsp+CDh] [rbp-33h]
  char v63; // [rsp+CFh] [rbp-31h]
  PCWSTR v64; // [rsp+D0h] [rbp-30h] BYREF
  HLOCAL *p_hMem; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v66; // [rsp+E0h] [rbp-20h] BYREF
  char v67; // [rsp+E8h] [rbp-18h]
  __int64 v68; // [rsp+F0h] [rbp-10h]
  __int64 v69; // [rsp+F8h] [rbp-8h] BYREF
  int v70; // [rsp+100h] [rbp+0h]
  __int128 v71; // [rsp+108h] [rbp+8h]
  __int64 v72; // [rsp+118h] [rbp+18h]
  __int64 v73; // [rsp+120h] [rbp+20h] BYREF
  int v74; // [rsp+128h] [rbp+28h]
  __int128 v75; // [rsp+130h] [rbp+30h]
  __int128 v76; // [rsp+140h] [rbp+40h]
  __int64 v77; // [rsp+150h] [rbp+50h] BYREF
  __int64 v78; // [rsp+158h] [rbp+58h] BYREF
  const WCHAR *v79; // [rsp+160h] [rbp+60h] BYREF
  HLOCAL *v80; // [rsp+168h] [rbp+68h] BYREF
  __int64 (__fastcall ***v81)(_QWORD, GUID *, __int64 *); // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  p_hMem = a3;
  v68 = a8;
  *(_DWORD *)v58 = a4;
  string = 0;
  v12 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING *))(*a2)[7])(a2, &string);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
      (const char *)(unsigned int)v12,
      v47);
    if ( string )
      WindowsDeleteString(string);
    return v13;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  _o__wcsicmp(L"enumerate.accounts.local", StringRawBuffer);
  if ( (unsigned int)dword_180175000 > 4 )
  {
    v55 = v68;
    v77 = a7;
    v78 = a6;
    v79 = a5;
    LODWORD(v51) = a4;
    v80 = a3;
    v81 = a2;
    v64 = WindowsGetStringRawBuffer(string, 0);
    *(_QWORD *)v59 = WindowsGetStringRawBuffer(string2, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v16,
      (unsigned int)&word_180157C0E,
      v17,
      v18,
      (__int64)v59,
      (__int64)&v64,
      (__int64)&v81,
      (__int64)&v80,
      (__int64)&v51,
      (__int64)&v79,
      (__int64)&v78,
      (__int64)&v77,
      (__int64)&v55);
  }
  if ( IsTokenCachingDisabled() )
  {
    if ( (unsigned int)dword_180175000 > 4 )
    {
      *(_QWORD *)v59 = "The test hook to disable caching is set";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v19,
        (unsigned int)byte_180157BD5,
        v20,
        v21,
        (__int64)v59);
    }
    if ( string )
      WindowsDeleteString(string);
    return 0;
  }
  *(_QWORD *)v59 = p_hMem;
  v60 = 0;
  v61 = *(_DWORD *)((char *)&v66 + 1);
  v62 = *(_WORD *)((char *)&v66 + 5);
  v63 = HIBYTE(v66);
  if ( (unsigned __int8)IsCacheEntryExpired(a5, v59) )
  {
    if ( (unsigned int)dword_180175000 > 2 )
    {
      *(_QWORD *)v59 = GetCurrentSystemTimeAsInt64();
      v64 = a5;
      LODWORD(v51) = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v22,
        (unsigned int)byte_180157B7D,
        v23,
        v24,
        (__int64)&v51,
        (__int64)&v64,
        (__int64)v59);
    }
LABEL_20:
    if ( string )
      WindowsDeleteString(string);
    return 2147942487LL;
  }
  v55 = a6;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v55);
  if ( !a6 )
  {
    if ( (unsigned int)dword_180175000 > 2 )
    {
      LODWORD(v51) = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180175000,
        (unsigned int)byte_180157B3D,
        0,
        v25,
        (__int64)&v51);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
    goto LABEL_20;
  }
  v54 = 0;
  v26 = (*a2)[6];
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  v27 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), struct Windows::Security::Credentials::IWebAccountProvider **))v26)(
          a2,
          &v54);
  v28 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D8,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
      (const char *)(unsigned int)v27,
      v47);
LABEL_25:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
    if ( string )
      WindowsDeleteString(string);
    return (unsigned int)v28;
  }
  v53 = 0;
  if ( a4 == 3 )
  {
    v51 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    v28 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0>>(
            v30,
            &v51);
    if ( v28 >= 0 )
    {
      v32 = v51;
      v33 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 64LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
      v28 = v33(v32, &v53);
      if ( v28 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
        goto LABEL_38;
      }
      v31 = 487;
    }
    else
    {
      v31 = 486;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
      (const char *)(unsigned int)v28,
      v47);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    goto LABEL_31;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  AllAccountsFromResponses = GetAllAccountsFromResponses(string2);
  v28 = AllAccountsFromResponses;
  if ( AllAccountsFromResponses < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DD,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
      (const char *)(unsigned int)AllAccountsFromResponses,
      v47);
LABEL_31:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    goto LABEL_25;
  }
LABEL_38:
  v57 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
  v34 = ChooseEffectiveAccountHints(v58, p_hMem, v53, &v57);
  v28 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
      (const char *)(unsigned int)v34,
      v47);
LABEL_40:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
    goto LABEL_31;
  }
  hMem = 0;
  LODWORD(SourceSize) = 0;
  p_hMem = &hMem;
  v66 = 0;
  v67 = 1;
  v28 = CreateRequestHash(a2, v57, 1, 1, &SourceSize, &v66);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x200,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
      (const char *)(unsigned int)v28,
      v48);
LABEL_43:
    v35 = hMem;
    hMem = 0;
    goto LABEL_44;
  }
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v36 = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromBytes(
          (Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v69,
          (unsigned __int8 *)hMem,
          (unsigned int)SourceSize);
  v28 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x207,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
      (const char *)(unsigned int)v36,
      v48);
    Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v69);
    goto LABEL_43;
  }
  v73 = 5;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v37 = v58[0];
  v38 = SerializeTokenCacheData(
          3,
          (int)hMem,
          SourceSize,
          (int)a5,
          v58[0],
          a6,
          v54,
          v53,
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter *)&v73);
  v39 = v38;
  if ( v38 >= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DelegatedTokenRequests>::GetImpl'::`2'::impl) )
    {
      *(_QWORD *)v58 = 0;
      v51 = 0;
      v41 = **a2;
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v51);
      v28 = v41(a2, &GUID_c8423c1d_aa94_48ea_86e5_4502f998ab78, &v51);
      if ( v28 < 0 )
      {
        v42 = 553;
LABEL_53:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v42,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
          (const char *)(unsigned int)v28,
          v49);
        _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v51);
        Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::~JsonObjectWriter((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter *)&v73);
        Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v69);
        v35 = hMem;
        hMem = 0;
LABEL_44:
        if ( v35 )
          LocalFree(v35);
        goto LABEL_40;
      }
      v28 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v51 + 48LL))(v51, v58);
      if ( v28 < 0 )
      {
        v42 = 555;
        goto LABEL_53;
      }
      LOBYTE(v49) = *(_QWORD *)v58 != 0;
      v28 = WriteTokenCacheEntry(string2, &v69, 2, &v73);
      if ( v28 < 0 )
      {
        v42 = 571;
        goto LABEL_53;
      }
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v51);
    }
    else
    {
      LOBYTE(v49) = 0;
      v46 = WriteTokenCacheEntry(string2, &v69, 2, &v73);
      v39 = v46;
      if ( v46 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
          (const char *)(unsigned int)v46,
          v49);
LABEL_63:
        Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::~JsonObjectWriter((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter *)&v73);
        Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v69);
        v40 = hMem;
        hMem = 0;
        goto LABEL_64;
      }
    }
    if ( a7 && IsTokenRequestLoggingEnabled() )
      SetCachedTokenRequest(
        (_DWORD)string2,
        (_DWORD)hMem,
        SourceSize,
        (_DWORD)a5,
        v37,
        (__int64)&v69,
        a7,
        (__int64)v54,
        v53);
    ClearAllCachedTokenRequestsAndResponses(string2, v43);
    v44 = (_DWORD *)v68;
    memcpy_s_3((void *const)(v68 + 4), v45, hMem, (unsigned int)SourceSize);
    *v44 = SourceSize;
    goto LABEL_63;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x21A,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
    (const char *)(unsigned int)v38,
    v49);
  Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::~JsonObjectWriter((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter *)&v73);
  Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v69);
  v40 = hMem;
  hMem = 0;
LABEL_64:
  if ( v40 )
    LocalFree(v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  if ( string )
    WindowsDeleteString(string);
  return v39;
}

```

## disassembly

```asm
0x18010cf14  push    rbp
0x18010cf16  push    rbx
0x18010cf17  push    rsi
0x18010cf18  push    rdi
0x18010cf19  push    r12
0x18010cf1b  push    r13
0x18010cf1d  push    r14
0x18010cf1f  push    r15
0x18010cf21  lea     rbp, [rsp-88h]
0x18010cf29  sub     rsp, 188h
0x18010cf30  mov     esi, r9d
0x18010cf33  mov     rdi, r8
0x18010cf36  mov     [rbp+0C0h+var_E8], r8
0x18010cf3a  mov     r15, rdx
0x18010cf3d  mov     r14, rcx
0x18010cf40  mov     rax, [rbp+0C0h+arg_38]
0x18010cf47  mov     [rbp+0C0h+var_D0], rax
0x18010cf4b  mov     dword ptr [rbp+0C0h+var_110], r9d
0x18010cf4f  mov     r12, [rbp+0C0h+arg_28]
0x18010cf56  mov     r13, [rbp+0C0h+arg_30]
0x18010cf5d  mov     [rbp+0C0h+string], 0
0x18010cf65  mov     rax, [rdx]
0x18010cf68  lea     rdx, [rbp+0C0h+string]
0x18010cf6c  mov     rcx, r15
0x18010cf6f  mov     rax, [rax+38h]
0x18010cf73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cf78  mov     ebx, eax
0x18010cf7a  test    eax, eax
0x18010cf7c  jns     short loc_18010CFB0
0x18010cf7e  mov     rcx, [rbp+0C8h]; this
0x18010cf85  mov     r9d, eax; char *
0x18010cf88  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010cf8f  mov     edx, 18Ch; void *
0x18010cf94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010cf99  nop
0x18010cf9a  mov     rcx, [rbp+0C0h+string]; string
0x18010cf9e  test    rcx, rcx
0x18010cfa1  jz      short loc_18010CFA9
0x18010cfa3  call    cs:__imp_WindowsDeleteString
0x18010cfa9  mov     eax, ebx
0x18010cfab  jmp     loc_18010D698
0x18010cfb0  xor     edx, edx; length
0x18010cfb2  mov     rcx, [rbp+0C0h+string]; string
0x18010cfb6  call    cs:__imp_WindowsGetStringRawBuffer
0x18010cfbc  mov     rdx, rax
0x18010cfbf  lea     rcx, aEnumerateAccou; "enumerate.accounts.local"
0x18010cfc6  call    cs:__imp__o__wcsicmp
0x18010cfcc  mov     eax, cs:dword_180175000
0x18010cfd2  mov     rbx, [rbp+0C0h+arg_20]
0x18010cfd9  cmp     eax, 4
0x18010cfdc  jbe     loc_18010D07F
0x18010cfe2  mov     rax, [rbp+0C0h+var_D0]
0x18010cfe6  mov     [rbp+0C0h+var_128], rax
0x18010cfea  mov     [rbp+0C0h+var_70], r13
0x18010cfee  mov     [rbp+0C0h+var_68], r12
0x18010cff2  mov     [rbp+0C0h+var_60], rbx
0x18010cff6  mov     dword ptr [rsp+1C0h+var_148], esi
0x18010cffa  mov     [rbp+0C0h+var_58], rdi
0x18010cffe  mov     [rbp+0C0h+var_50], r15
0x18010d002  xor     edx, edx; length
0x18010d004  mov     rcx, [rbp+0C0h+string]; string
0x18010d008  call    cs:__imp_WindowsGetStringRawBuffer
0x18010d00e  mov     [rbp+0C0h+var_F0], rax
0x18010d012  xor     edx, edx; length
0x18010d014  mov     rcx, r14; string
0x18010d017  call    cs:__imp_WindowsGetStringRawBuffer
0x18010d01d  mov     qword ptr [rbp+0C0h+var_100], rax
0x18010d021  lea     rax, [rbp+0C0h+var_128]
0x18010d025  mov     [rsp+1C0h+var_160], rax
0x18010d02a  lea     rax, [rbp+0C0h+var_70]
0x18010d02e  mov     [rsp+1C0h+var_168], rax
0x18010d033  lea     rax, [rbp+0C0h+var_68]
0x18010d037  mov     [rsp+1C0h+var_170], rax
0x18010d03c  lea     rax, [rbp+0C0h+var_60]
0x18010d040  mov     [rsp+1C0h+var_178], rax
0x18010d045  lea     rax, [rsp+1C0h+var_148]
0x18010d04a  mov     [rsp+1C0h+var_180], rax
0x18010d04f  lea     rax, [rbp+0C0h+var_58]
0x18010d053  mov     [rsp+1C0h+var_188], rax
0x18010d058  lea     rax, [rbp+0C0h+var_50]
0x18010d05c  mov     [rsp+1C0h+var_190], rax
0x18010d061  lea     rax, [rbp+0C0h+var_F0]
0x18010d065  mov     [rsp+1C0h+var_198], rax
0x18010d06a  lea     rax, [rbp+0C0h+var_100]
0x18010d06e  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x18010d073  lea     rdx, word_180157C0E
0x18010d07a  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$07@@U2@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$07@@4AEBU?$_tlgWrapperByVal@$03@@4444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18010d07f  call    ?IsTokenCachingDisabled@@YA_NXZ; IsTokenCachingDisabled(void)
0x18010d084  test    al, al
0x18010d086  jz      short loc_18010D0CA
0x18010d088  mov     eax, cs:dword_180175000
0x18010d08e  cmp     eax, 4
0x18010d091  jbe     short loc_18010D0B4
0x18010d093  lea     rax, aTheTestHookToD; "The test hook to disable caching is set"
0x18010d09a  mov     qword ptr [rbp+0C0h+var_100], rax
0x18010d09e  lea     rax, [rbp+0C0h+var_100]
0x18010d0a2  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18010d0a7  lea     rdx, byte_180157BD5
0x18010d0ae  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18010d0b3  nop
0x18010d0b4  mov     rcx, [rbp+0C0h+string]; string
0x18010d0b8  test    rcx, rcx
0x18010d0bb  jz      short loc_18010D0C3
0x18010d0bd  call    cs:__imp_WindowsDeleteString
0x18010d0c3  xor     eax, eax
0x18010d0c5  jmp     loc_18010D698
0x18010d0ca  mov     rax, [rbp+0C0h+var_E8]
0x18010d0ce  mov     qword ptr [rbp+0C0h+var_100], rax
0x18010d0d2  mov     [rbp+0C0h+var_F8], 0
0x18010d0d6  mov     eax, [rbp+0C0h+var_DF]
0x18010d0d9  mov     [rbp+0C0h+var_F7], eax
0x18010d0dc  movzx   eax, [rbp+0C0h+var_DB]
0x18010d0e0  mov     [rbp+0C0h+var_F3], ax
0x18010d0e4  mov     al, [rbp+0C0h+var_D9]
0x18010d0e7  mov     [rbp+0C0h+var_F1], al
0x18010d0ea  lea     rdx, [rbp+0C0h+var_100]
0x18010d0ee  mov     rcx, rbx
0x18010d0f1  call    ?IsCacheEntryExpired@@YA_N_JV?$optional@_J@std@@@Z; IsCacheEntryExpired(__int64,std::optional<__int64>)
0x18010d0f6  test    al, al
0x18010d0f8  jz      short loc_18010D148
0x18010d0fa  mov     eax, cs:dword_180175000
0x18010d100  cmp     eax, 2
0x18010d103  jbe     loc_18010D199
0x18010d109  call    ?GetCurrentSystemTimeAsInt64@@YA_JXZ; GetCurrentSystemTimeAsInt64(void)
0x18010d10e  mov     qword ptr [rbp+0C0h+var_100], rax
0x18010d112  mov     [rbp+0C0h+var_F0], rbx
0x18010d116  mov     dword ptr [rsp+1C0h+var_148], 80070057h
0x18010d11e  lea     rax, [rbp+0C0h+var_100]
0x18010d122  mov     [rsp+1C0h+var_190], rax
0x18010d127  lea     rax, [rbp+0C0h+var_F0]
0x18010d12b  mov     [rsp+1C0h+var_198], rax
0x18010d130  lea     rax, [rsp+1C0h+var_148]
0x18010d135  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18010d13a  lea     rdx, byte_180157B7D
0x18010d141  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18010d146  jmp     short loc_18010D199
0x18010d148  mov     [rbp+0C0h+var_128], r12
0x18010d14c  lea     rcx, [rbp+0C0h+var_128]
0x18010d150  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18010d155  nop
0x18010d156  test    r12, r12
0x18010d159  jnz     short loc_18010D1B2
0x18010d15b  mov     eax, cs:dword_180175000
0x18010d161  cmp     eax, 2
0x18010d164  jbe     short loc_18010D18F
0x18010d166  mov     dword ptr [rsp+1C0h+var_148], 80070057h
0x18010d16e  lea     rax, [rsp+1C0h+var_148]
0x18010d173  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18010d178  xor     r8d, r8d
0x18010d17b  lea     rdx, byte_180157B3D
0x18010d182  lea     rcx, dword_180175000
0x18010d189  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18010d18e  nop
0x18010d18f  lea     rcx, [rbp+0C0h+var_128]
0x18010d193  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010d198  nop
0x18010d199  mov     rcx, [rbp+0C0h+string]; string
0x18010d19d  test    rcx, rcx
0x18010d1a0  jz      short loc_18010D1A8
0x18010d1a2  call    cs:__imp_WindowsDeleteString
0x18010d1a8  mov     eax, 80070057h
0x18010d1ad  jmp     loc_18010D698
0x18010d1b2  mov     [rbp+0C0h+var_130], 0
0x18010d1ba  mov     rax, [r15]
0x18010d1bd  mov     rdi, [rax+30h]
0x18010d1c1  lea     rcx, [rbp+0C0h+var_130]
0x18010d1c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010d1ca  lea     rdx, [rbp+0C0h+var_130]
0x18010d1ce  mov     rcx, r15
0x18010d1d1  mov     rax, rdi
0x18010d1d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d1d9  mov     edi, eax
0x18010d1db  test    eax, eax
0x18010d1dd  jns     short loc_18010D225
0x18010d1df  mov     rcx, [rbp+0C8h]; this
0x18010d1e6  mov     r9d, eax; char *
0x18010d1e9  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010d1f0  mov     edx, 1D8h; void *
0x18010d1f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d1fa  nop
0x18010d1fb  lea     rcx, [rbp+0C0h+var_130]
0x18010d1ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010d204  nop
0x18010d205  lea     rcx, [rbp+0C0h+var_128]
0x18010d209  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010d20e  nop
0x18010d20f  mov     rcx, [rbp+0C0h+string]; string
0x18010d213  test    rcx, rcx
0x18010d216  jz      short loc_18010D21E
0x18010d218  call    cs:__imp_WindowsDeleteString
0x18010d21e  mov     eax, edi
0x18010d220  jmp     loc_18010D698
0x18010d225  mov     [rbp+0C0h+var_138], 0
0x18010d22d  cmp     esi, 3
0x18010d230  jz      short loc_18010D284
0x18010d232  lea     rcx, [rbp+0C0h+var_138]
0x18010d236  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010d23b  lea     r9, [rbp+0C0h+var_138]
0x18010d23f  mov     r8, r12
0x18010d242  mov     rdx, [rbp+0C0h+var_130]
0x18010d246  mov     rcx, r14; string2
0x18010d249  call    ?GetAllAccountsFromResponses@@YAJPEAUHSTRING__@@PEAUIWebAccountProvider@Credentials@Security@Windows@@PEAUIBuffer@Streams@Storage@5@PEAPEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@@Z; GetAllAccountsFromResponses(HSTRING__ *,Windows::Security::Credentials::IWebAccountProvider *,Windows::Storage::Streams::IBuffer *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> * *)
0x18010d24e  mov     edi, eax
0x18010d250  xor     esi, esi
0x18010d252  test    eax, eax
0x18010d254  jns     loc_18010D30C
0x18010d25a  mov     rcx, [rbp+0C8h]; this
0x18010d261  mov     r9d, eax; char *
0x18010d264  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010d26b  mov     edx, 1DDh; void *
0x18010d270  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d275  nop
0x18010d276  lea     rcx, [rbp+0C0h+var_138]
0x18010d27a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010d27f  jmp     loc_18010D1FB
0x18010d284  mov     [rsp+1C0h+var_148], 0
0x18010d28d  lea     rcx, [rsp+1C0h+var_148]
0x18010d292  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010d297  lea     rdx, [rsp+1C0h+var_148]
0x18010d29c  call    ??$CreateExternalObjectVector@VWebAccount@Credentials@Security@Windows@@V?$AgileVector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@$0A@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0> * *)
0x18010d2a1  mov     edi, eax
0x18010d2a3  test    eax, eax
0x18010d2a5  jns     short loc_18010D2CF
0x18010d2a7  mov     edx, 1E6h; void *
0x18010d2ac  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010d2b3  mov     r9d, edi; char *
0x18010d2b6  mov     rcx, [rbp+0C8h]; this
0x18010d2bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d2c2  nop
0x18010d2c3  lea     rcx, [rsp+1C0h+var_148]
0x18010d2c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010d2cd  jmp     short loc_18010D276
0x18010d2cf  mov     rsi, [rsp+1C0h+var_148]
0x18010d2d4  mov     rax, [rsi]
0x18010d2d7  mov     rdi, [rax+40h]
0x18010d2db  lea     rcx, [rbp+0C0h+var_138]
0x18010d2df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010d2e4  lea     rdx, [rbp+0C0h+var_138]
0x18010d2e8  mov     rcx, rsi
0x18010d2eb  mov     rax, rdi
0x18010d2ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d2f3  mov     edi, eax
0x18010d2f5  xor     esi, esi
0x18010d2f7  test    eax, eax
0x18010d2f9  jns     short loc_18010D302
0x18010d2fb  mov     edx, 1E7h
0x18010d300  jmp     short loc_18010D2AC
0x18010d302  lea     rcx, [rsp+1C0h+var_148]
0x18010d307  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010d30c  mov     [rbp+0C0h+var_118], rsi
0x18010d310  lea     rcx, [rbp+0C0h+var_118]
0x18010d314  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010d319  lea     r9, [rbp+0C0h+var_118]
0x18010d31d  mov     r8, [rbp+0C0h+var_138]
0x18010d321  mov     rdx, [rbp+0C0h+var_E8]
0x18010d325  lea     rcx, [rbp+0C0h+var_110]
0x18010d329  call    ?ChooseEffectiveAccountHints@@YAJPEAW4WebTokenRequestStatus@Core@Web@Authentication@Security@Windows@@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@6@1PEAPEAU7896@@Z; ChooseEffectiveAccountHints(Windows::Security::Authentication::Web::Core::WebTokenRequestStatus *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> * *)
0x18010d32e  mov     edi, eax
0x18010d330  test    eax, eax
0x18010d332  jns     short loc_18010D35E
0x18010d334  mov     rcx, [rbp+0C8h]; this
0x18010d33b  mov     r9d, eax; char *
0x18010d33e  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010d345  mov     edx, 1EFh; void *
0x18010d34a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d34f  nop
0x18010d350  lea     rcx, [rbp+0C0h+var_118]
0x18010d354  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010d359  jmp     loc_18010D276
0x18010d35e  mov     [rsp+1C0h+hMem], rsi
0x18010d363  mov     dword ptr [rbp+0C0h+SourceSize], esi
0x18010d366  lea     rax, [rsp+1C0h+hMem]
0x18010d36b  mov     [rbp+0C0h+var_E8], rax
0x18010d36f  mov     [rbp-20h], rsi
0x18010d373  mov     [rbp+0C0h+var_D8], 1
0x18010d377  lea     rax, [rbp+0C0h+var_E0]
0x18010d37b  mov     [rsp+1C0h+var_198], rax
0x18010d380  lea     rax, [rbp+0C0h+SourceSize]
0x18010d384  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x18010d389  mov     r9b, 1
0x18010d38c  mov     r8b, r9b
0x18010d38f  mov     rdx, [rbp+0C0h+var_118]
0x18010d393  mov     rcx, r15
0x18010d396  call    ?CreateRequestHash@@YAJPEAUIWebTokenRequest@Core@Web@Authentication@Security@Windows@@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@6@_N2PEAKPEAPEAE@Z; CreateRequestHash(Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,bool,bool,ulong *,uchar * *)
0x18010d39b  mov     edi, eax
0x18010d39d  lea     rcx, [rbp+0C0h+var_E8]
0x18010d3a1  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18010d3a6  test    edi, edi
0x18010d3a8  jns     short loc_18010D3E4
0x18010d3aa  mov     rcx, [rbp+0C8h]; this
0x18010d3b1  mov     r9d, edi; char *
0x18010d3b4  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010d3bb  mov     edx, 200h; void *
0x18010d3c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d3c5  nop
0x18010d3c6  mov     rcx, [rsp+1C0h+hMem]; hMem
0x18010d3cb  mov     [rsp+1C0h+hMem], rsi
0x18010d3d0  test    rcx, rcx
0x18010d3d3  jz      loc_18010D350
0x18010d3d9  call    cs:__imp_LocalFree
  ... truncated ...
```
