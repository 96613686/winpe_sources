# Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::WriteAllObjectIdsForTypeToCache(Windows::Internal::Security::Authentication::Web::IWamObjectStore *,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,HSTRING__ * const,std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>,std::allocator<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>>> &)

- ea: `0x1800787a0`
- end: `0x180078db7`
- name: `?WriteAllObjectIdsForTypeToCache@StoredObjectInfoWithCache@TokenBroker@Authentication@Security@Internal@Windows@@CAJPEAUIWamObjectStore@Web@3456@W4StoredObjectType@23456@QEAUHSTRING__@@AEAV?$vector@V?$shared_ptr@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@V?$allocator@V?$shared_ptr@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@2@@std@@@Z`
- size: `1559`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18005a8ec`

## callees

- `0x180007350`
- `0x180008fb0`
- `0x18000bd40`
- `0x18000d250`
- `0x18001a510`
- `0x18003df30`
- `0x180043370`
- `0x180044d30`
- `0x180045a04`
- `0x180047334`
- `0x180048694`
- `0x18004d328`
- `0x18004d3a4`
- `0x18004d844`
- `0x180055498`
- `0x180060750`
- `0x180061720`
- `0x1800787a0`
- `0x18008e690`
- `0x180091975`
- `0x180111020`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078a2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078a2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800787fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800788f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800787fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800788f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078c48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078d65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078d84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078c48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078d65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078d84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180078b58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180078b58`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007895e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007895e`
- `ext-ms-win-kernel32-package-l1-1-0!AppContainerDeriveSidFromMoniker` at `0x1800788fe`
- `ext-ms-win-kernel32-package-l1-1-0!AppContainerDeriveSidFromMoniker` at `0x1800788fe`

## string_xrefs

- `0x180078c5e`: `Windows.Storage.Streams.DataWriter`
- `0x18007889e`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180078917`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x18007899a`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180078a06`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180078c04`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180078c21`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180078c8b`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::WriteAllObjectIdsForTypeToCache(
        __int64 a1,
        unsigned int a2,
        HSTRING a3,
        Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId ***a4)
{
  HSTRING v5; // rbx
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  const struct Windows::Internal::String *v9; // rax
  int v10; // eax
  signed int BaseHexByteString; // r14d
  HSTRING v12; // rcx
  PCWSTR StringRawBuffer; // rax
  int v14; // eax
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // eax
  signed int AllObjectsCacheKey; // eax
  __int64 v19; // rdx
  __int64 v20; // r9
  HSTRING v21; // rcx
  signed int LastError; // eax
  Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId **v23; // rdi
  Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId **v24; // r15
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rsi
  unsigned __int64 v27; // rax
  unsigned __int64 v28; // rcx
  SIZE_T v29; // r9
  LPVOID v30; // rax
  LPVOID v31; // rsi
  HSTRING v32; // rdi
  Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId **v33; // r12
  Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId **v34; // r13
  _WORD *v35; // r15
  __int64 v36; // r14
  size_t v37; // r14
  int v38; // eax
  _QWORD *v39; // rax
  int v40; // eax
  __int64 v41; // rdx
  int v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v45; // [rsp+38h] [rbp-C8h] BYREF
  PSID v46; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v47[3]; // [rsp+48h] [rbp-B8h] BYREF
  char v48; // [rsp+60h] [rbp-A0h]
  HSTRING v49; // [rsp+68h] [rbp-98h] BYREF
  void *Src; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v51; // [rsp+78h] [rbp-88h] BYREF
  SIZE_T cb; // [rsp+80h] [rbp-80h] BYREF
  HSTRING string; // [rsp+88h] [rbp-78h] BYREF
  PSID Sid; // [rsp+90h] [rbp-70h] BYREF
  LPWSTR StringSid; // [rsp+98h] [rbp-68h] BYREF
  __int64 v56; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v57; // [rsp+A8h] [rbp-58h]
  HSTRING v58[4]; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING v59[4]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]
  unsigned int v61; // [rsp+158h] [rbp+58h] BYREF

  v61 = a2;
  v57 = a1;
  string = a3;
  v44 = 0;
  v56 = 0;
  StringSid = 0;
  v5 = 0;
  v51 = 0;
  if ( (unsigned int)dword_180175000 > 4 )
  {
    Sid = (PSID)WindowsGetStringRawBuffer(string, 0);
    LODWORD(Src) = v61;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v6,
      (unsigned int)byte_180159411,
      v7,
      v8,
      (__int64)&Src,
      (__int64)&Sid);
  }
  v47[0] = &v44;
  v47[1] = &v61;
  v47[2] = &string;
  v48 = 1;
  v58[0] = string;
  v9 = (const struct Windows::Internal::String *)Windows::Internal::StringReference::StringReference(
                                                   v59,
                                                   L"NO_APPLICATION");
  if ( (unsigned int)Windows::Internal::StringReference::CompareOrdinal((Windows::Internal::StringReference *)v58, v9) )
  {
    v45 = 0;
    Sid = 0;
    v46 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v14 = AppContainerDeriveSidFromMoniker(StringRawBuffer, &Sid);
    BaseHexByteString = v14;
    v44 = v14;
    if ( v14 < 0 )
    {
      v15 = (unsigned int)v14;
      v16 = 1951;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
        (const char *)v15,
        v43);
      std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>::~unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>(&v46);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v45);
      v48 = 0;
      lambda_e0349bfe1da25ea74fad606643c17560_::operator()(v47);
      goto LABEL_73;
    }
    v46 = Sid;
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v45,
        StringSid);
      v17 = Windows::Internal::String::Initialize<unsigned short *>(&v51, &StringSid);
      BaseHexByteString = v17;
      v44 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7A5,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
          (const char *)(unsigned int)v17,
          v43);
        std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>::~unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>(&v46);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v45);
LABEL_6:
        v48 = 0;
        lambda_e0349bfe1da25ea74fad606643c17560_::operator()(v47);
        v12 = v51;
        if ( v51 )
LABEL_72:
          WindowsDeleteString(v12);
        goto LABEL_73;
      }
      v5 = v51;
    }
    else
    {
      LastError = GetLastError();
      BaseHexByteString = LastError;
      if ( LastError > 0 )
        BaseHexByteString = (unsigned __int16)LastError | 0x80070000;
      v44 = BaseHexByteString;
      if ( BaseHexByteString < 0 )
      {
        v15 = (unsigned int)BaseHexByteString;
        v16 = 1961;
        goto LABEL_11;
      }
    }
    std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>::~unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>(&v46);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v45);
    goto LABEL_17;
  }
  v10 = Windows::Internal::String::Initialize((Windows::Internal::String *)&v51, L"S-1-5-10", 8u);
  BaseHexByteString = v10;
  v44 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x793,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)(unsigned int)v10,
      v43);
    goto LABEL_6;
  }
  v5 = v51;
LABEL_17:
  v49 = 0;
  AllObjectsCacheKey = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::GetAllObjectsCacheKey(
                         v61,
                         string,
                         &v49);
  BaseHexByteString = AllObjectsCacheKey;
  v44 = AllObjectsCacheKey;
  if ( AllObjectsCacheKey < 0 )
  {
    v19 = 1966;
    goto LABEL_19;
  }
  v23 = *a4;
  v24 = a4[1];
  v25 = 0;
  if ( *a4 != v24 )
  {
    v26 = 0;
    while ( 1 )
    {
      cb = 0;
      AllObjectsCacheKey = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::GetBaseHexByteString(
                             *v23,
                             (const unsigned __int16 **)&cb);
      BaseHexByteString = AllObjectsCacheKey;
      v44 = AllObjectsCacheKey;
      if ( AllObjectsCacheKey < 0 )
        break;
      v27 = -1;
      do
        ++v27;
      while ( *(_WORD *)(cb + 2 * v27) );
      v28 = v27 + 1;
      if ( v27 + 1 < v27 )
      {
        BaseHexByteString = -2147024362;
        v44 = -2147024362;
        v20 = 2147942934LL;
        v19 = 1979;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
          (const char *)v20,
          v43);
        v21 = v49;
        if ( v49 )
LABEL_68:
          WindowsDeleteString(v21);
        goto LABEL_69;
      }
      v25 = v26 + v28;
      if ( v26 + v28 < v26 )
      {
        BaseHexByteString = -2147024362;
        v44 = -2147024362;
        v20 = 2147942934LL;
        v19 = 1980;
        goto LABEL_20;
      }
      v44 = 0;
      v23 += 2;
      v26 += v28;
      if ( v23 == v24 )
        goto LABEL_34;
    }
    v19 = 1977;
LABEL_19:
    v20 = (unsigned int)AllObjectsCacheKey;
    goto LABEL_20;
  }
LABEL_34:
  v29 = -1;
  if ( v25 + 1 >= v25 )
    v29 = v25 + 1;
  AllObjectsCacheKey = v25 + 1 < v25 ? 0x80070216 : 0;
  BaseHexByteString = AllObjectsCacheKey;
  cb = v29;
  v44 = AllObjectsCacheKey;
  if ( v25 + 1 < v25 )
  {
    v19 = 1987;
    goto LABEL_19;
  }
  AllObjectsCacheKey = ULongLongMult(v29, 2u, &cb);
  BaseHexByteString = AllObjectsCacheKey;
  v44 = AllObjectsCacheKey;
  if ( AllObjectsCacheKey < 0 )
  {
    v19 = 1988;
    goto LABEL_19;
  }
  v30 = CoTaskMemAlloc(cb);
  v31 = v30;
  v46 = v30;
  v32 = v49;
  if ( !v30 )
  {
    BaseHexByteString = -2147024882;
    v44 = -2147024882;
    goto LABEL_66;
  }
  v33 = *a4;
  v34 = a4[1];
  v35 = v30;
  while ( 1 )
  {
    if ( v33 == v34 )
    {
      *v35 = 0;
      LODWORD(Src) = 0;
      v38 = ULongLongToULong(cb, (unsigned int *)&Src);
      BaseHexByteString = v38;
      v44 = v38;
      if ( v38 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7DC,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
          (const char *)(unsigned int)v38,
          v43);
        goto LABEL_66;
      }
      v45 = 0;
      v39 = (_QWORD *)Windows::Internal::StringReference::StringReference(v59, L"Windows.Storage.Streams.DataWriter");
      v40 = Windows::Foundation::ActivateInstance<Windows::Storage::Streams::IDataWriter>(*v39, &v45);
      BaseHexByteString = v40;
      v44 = v40;
      if ( v40 < 0 )
      {
        v41 = 2015;
LABEL_57:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v41,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
          (const char *)(unsigned int)v40,
          v43);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        goto LABEL_66;
      }
      v40 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID))(*(_QWORD *)v45 + 96LL))(v45, (unsigned int)Src, v31);
      BaseHexByteString = v40;
      v44 = v40;
      if ( v40 < 0 )
      {
        v41 = 2016;
        goto LABEL_57;
      }
      v40 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 248LL))(v45, &v56);
      BaseHexByteString = v40;
      v44 = v40;
      if ( v40 < 0 )
      {
        v41 = 2017;
        goto LABEL_57;
      }
      v40 = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64))(*(_QWORD *)v57 + 56LL))(v57, v32, v5, v56);
      BaseHexByteString = v40;
      v44 = v40;
      if ( v40 < 0 )
      {
        v41 = 2019;
        goto LABEL_57;
      }
      v44 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      BaseHexByteString = v44;
LABEL_66:
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v46);
      if ( v32 )
      {
        v21 = v32;
        goto LABEL_68;
      }
LABEL_69:
      v48 = 0;
      goto LABEL_70;
    }
    Src = 0;
    BaseHexByteString = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::GetBaseHexByteString(
                          *v33,
                          (const unsigned __int16 **)&Src);
    v44 = BaseHexByteString;
    if ( BaseHexByteString < 0 )
      break;
    v36 = -1;
    do
      ++v36;
    while ( *((_WORD *)Src + v36) );
    v37 = 2 * v36 + 2;
    memcpy_0(v35, Src, v37);
    v35 = (_WORD *)((char *)v35 + v37);
    v33 += 2;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7D3,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
    (const char *)(unsigned int)BaseHexByteString,
    v43);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v46);
  if ( v32 )
    WindowsDeleteString(v32);
  v48 = 0;
LABEL_70:
  lambda_e0349bfe1da25ea74fad606643c17560_::operator()(v47);
  if ( v5 )
  {
    v12 = v5;
    goto LABEL_72;
  }
LABEL_73:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
  return (unsigned int)BaseHexByteString;
}

```

## disassembly

```asm
0x1800787a0  mov     [rsp-8+arg_8], edx
0x1800787a4  push    rbp
0x1800787a5  push    rbx
0x1800787a6  push    rsi
0x1800787a7  push    rdi
0x1800787a8  push    r12
0x1800787aa  push    r13
0x1800787ac  push    r14
0x1800787ae  push    r15
0x1800787b0  lea     rbp, [rsp-8]
0x1800787b5  sub     rsp, 108h
0x1800787bc  mov     rax, cs:__security_cookie
0x1800787c3  xor     rax, rsp
0x1800787c6  mov     [rbp+40h+var_50], rax
0x1800787ca  mov     r13, r9
0x1800787cd  mov     [rbp+40h+var_98], rcx
0x1800787d1  mov     [rbp+40h+string], r8
0x1800787d5  xor     r12d, r12d
0x1800787d8  mov     [rsp+140h+var_110], r12d
0x1800787dd  mov     [rbp+40h+var_A0], r12
0x1800787e1  mov     [rbp+40h+StringSid], r12
0x1800787e5  mov     ebx, r12d
0x1800787e8  mov     [rsp+140h+var_C8], rbx
0x1800787ed  mov     eax, cs:dword_180175000
0x1800787f3  cmp     eax, 4
0x1800787f6  jbe     short loc_18007882E
0x1800787f8  xor     edx, edx; length
0x1800787fa  mov     rcx, [rbp+40h+string]; string
0x1800787fe  call    cs:__imp_WindowsGetStringRawBuffer
0x180078804  mov     [rbp+40h+Sid], rax
0x180078808  mov     eax, [rbp+40h+arg_8]
0x18007880b  mov     dword ptr [rsp+140h+Src], eax
0x18007880f  lea     rax, [rbp+40h+Sid]
0x180078813  mov     [rsp+140h+var_118], rax
0x180078818  lea     rax, [rsp+140h+Src]
0x18007881d  mov     qword ptr [rsp+140h+var_120], rax; int
0x180078822  lea     rdx, byte_180159411
0x180078829  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18007882e  lea     rax, [rsp+140h+var_110]
0x180078833  mov     [rsp+140h+var_F8], rax
0x180078838  lea     rax, [rbp+40h+arg_8]
0x18007883c  mov     [rsp+140h+var_F0], rax
0x180078841  lea     rax, [rbp+40h+string]
0x180078845  mov     [rsp+140h+var_E8], rax
0x18007884a  mov     [rsp+140h+var_E0], 1
0x18007884f  mov     rax, [rbp+40h+string]
0x180078853  mov     [rbp+40h+var_90], rax
0x180078857  lea     rdx, aNoApplication; "NO_APPLICATION"
0x18007885e  lea     rcx, [rbp+40h+var_70]; string
0x180078862  call    ??$?0$0P@@StringReference@Internal@Windows@@QEAA@AEAY0P@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[15])
0x180078867  mov     rdx, rax; struct Windows::Internal::String *
0x18007886a  lea     rcx, [rbp+40h+var_90]; this
0x18007886e  call    ?CompareOrdinal@StringReference@Internal@Windows@@QEBAHAEBVString@23@@Z; Windows::Internal::StringReference::CompareOrdinal(Windows::Internal::String const &)
0x180078873  test    eax, eax
0x180078875  jnz     short loc_1800788DD
0x180078877  lea     r8d, [rax+8]; unsigned int
0x18007887b  lea     rdx, aS1510; "S-1-5-10"
0x180078882  lea     rcx, [rsp+140h+var_C8]; this
0x180078887  call    ?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z; Windows::Internal::String::Initialize(ushort const *,uint)
0x18007888c  mov     r14d, eax
0x18007888f  mov     [rsp+140h+var_110], eax
0x180078893  test    eax, eax
0x180078895  jns     short loc_1800788D3
0x180078897  mov     rcx, [rbp+48h]; this
0x18007889b  mov     r9d, eax; char *
0x18007889e  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800788a5  mov     edx, 793h; void *
0x1800788aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800788af  nop
0x1800788b0  mov     [rsp+140h+var_E0], r12b
0x1800788b5  lea     rcx, [rsp+140h+var_F8]
0x1800788ba  call    _lambda_e0349bfe1da25ea74fad606643c17560___operator__
0x1800788bf  nop
0x1800788c0  mov     rcx, [rsp+140h+var_C8]
0x1800788c5  test    rcx, rcx
0x1800788c8  jz      loc_180078D8B
0x1800788ce  jmp     loc_180078D84
0x1800788d3  mov     rbx, [rsp+140h+var_C8]
0x1800788d8  jmp     loc_1800789DD
0x1800788dd  mov     [rsp+140h+var_108], r12
0x1800788e2  mov     [rbp+40h+Sid], r12
0x1800788e6  mov     [rsp+140h+var_100], r12
0x1800788eb  xor     edx, edx; length
0x1800788ed  mov     rcx, [rbp+40h+string]; string
0x1800788f1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800788f7  lea     rdx, [rbp+40h+Sid]
0x1800788fb  mov     rcx, rax
0x1800788fe  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x180078904  mov     r14d, eax
0x180078907  mov     [rsp+140h+var_110], eax
0x18007890b  test    eax, eax
0x18007890d  jns     short loc_180078951
0x18007890f  mov     r9d, eax; char *
0x180078912  mov     edx, 79Fh; void *
0x180078917  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18007891e  mov     rcx, [rbp+48h]; this
0x180078922  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078927  lea     rcx, [rsp+140h+var_100]
0x18007892c  call    ??1?$unique_ptr@PEAXUSidDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@QEAA@XZ; std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>::~unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>(void)
0x180078931  lea     rcx, [rsp+140h+var_108]
0x180078936  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18007893b  nop
0x18007893c  mov     [rsp+140h+var_E0], r12b
0x180078941  lea     rcx, [rsp+140h+var_F8]
0x180078946  call    _lambda_e0349bfe1da25ea74fad606643c17560___operator__
0x18007894b  nop
0x18007894c  jmp     loc_180078D8B
0x180078951  mov     rcx, [rbp+40h+Sid]; Sid
0x180078955  mov     [rsp+140h+var_100], rcx
0x18007895a  lea     rdx, [rbp+40h+StringSid]; StringSid
0x18007895e  call    cs:__imp_ConvertSidToStringSidW
0x180078964  test    eax, eax
0x180078966  jz      loc_180078A2A
0x18007896c  mov     rdx, [rbp+40h+StringSid]
0x180078970  lea     rcx, [rsp+140h+var_108]
0x180078975  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18007897a  lea     rdx, [rbp+40h+StringSid]
0x18007897e  lea     rcx, [rsp+140h+var_C8]
0x180078983  call    ??$Initialize@PEAG@String@Internal@Windows@@QEAAJAEBQEAGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort *>(ushort * const &,Windows::Internal::_StringDetail::dummy_t)
0x180078988  mov     r14d, eax
0x18007898b  mov     [rsp+140h+var_110], eax
0x18007898f  test    eax, eax
0x180078991  jns     short loc_1800789C4
0x180078993  mov     rcx, [rbp+48h]; this
0x180078997  mov     r9d, eax; char *
0x18007899a  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800789a1  mov     edx, 7A5h; void *
0x1800789a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800789ab  lea     rcx, [rsp+140h+var_100]
0x1800789b0  call    ??1?$unique_ptr@PEAXUSidDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@QEAA@XZ; std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>::~unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>(void)
0x1800789b5  lea     rcx, [rsp+140h+var_108]
0x1800789ba  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800789bf  jmp     loc_1800788B0
0x1800789c4  mov     rbx, [rsp+140h+var_C8]
0x1800789c9  lea     rcx, [rsp+140h+var_100]
0x1800789ce  call    ??1?$unique_ptr@PEAXUSidDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@QEAA@XZ; std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>::~unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>(void)
0x1800789d3  lea     rcx, [rsp+140h+var_108]
0x1800789d8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800789dd  mov     [rsp+140h+var_D8], r12
0x1800789e2  lea     r8, [rsp+140h+var_D8]
0x1800789e7  mov     rdx, [rbp+40h+string]
0x1800789eb  mov     ecx, [rbp+40h+arg_8]
0x1800789ee  call    ?GetAllObjectsCacheKey@StoredObjectInfoWithCache@TokenBroker@Authentication@Security@Internal@Windows@@SAJW4StoredObjectType@23456@QEAUHSTRING__@@AEAVString@56@@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::GetAllObjectsCacheKey(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,HSTRING__ * const,Windows::Internal::String &)
0x1800789f3  mov     r14d, eax
0x1800789f6  mov     [rsp+140h+var_110], eax
0x1800789fa  test    eax, eax
0x1800789fc  jns     short loc_180078A5D
0x1800789fe  mov     edx, 7AEh; void *
0x180078a03  mov     r9d, eax; char *
0x180078a06  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180078a0d  mov     rcx, [rbp+48h]; this
0x180078a11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078a16  nop
0x180078a17  mov     rcx, [rsp+140h+var_D8]
0x180078a1c  test    rcx, rcx
0x180078a1f  jz      loc_180078D6C
0x180078a25  jmp     loc_180078D65
0x180078a2a  call    cs:__imp_GetLastError
0x180078a30  mov     r14d, eax
0x180078a33  test    eax, eax
0x180078a35  jle     short loc_180078A42
0x180078a37  movzx   r14d, ax
0x180078a3b  or      r14d, 80070000h
0x180078a42  mov     [rsp+140h+var_110], r14d
0x180078a47  test    r14d, r14d
0x180078a4a  jns     loc_1800789C9
0x180078a50  mov     r9d, r14d
0x180078a53  mov     edx, 7A9h
0x180078a58  jmp     loc_180078917
0x180078a5d  mov     rdi, [r13+0]
0x180078a61  mov     r15, [r13+8]
0x180078a65  mov     rdx, r12
0x180078a68  cmp     rdi, r15
0x180078a6b  jz      short loc_180078AC4
0x180078a6d  mov     rsi, r12
0x180078a70  mov     [rbp+40h+cb], r12
0x180078a74  lea     rdx, [rbp+40h+cb]; unsigned __int16 **
0x180078a78  mov     rcx, [rdi]; this
0x180078a7b  call    ?GetBaseHexByteString@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAPEBG@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::GetBaseHexByteString(ushort const * *)
0x180078a80  mov     r14d, eax
0x180078a83  mov     [rsp+140h+var_110], eax
0x180078a87  test    eax, eax
0x180078a89  js      loc_180078B24
0x180078a8f  mov     rcx, [rbp+40h+cb]
0x180078a93  or      rax, 0FFFFFFFFFFFFFFFFh
0x180078a97  inc     rax
0x180078a9a  cmp     [rcx+rax*2], r12w
0x180078a9f  jnz     short loc_180078A97
0x180078aa1  lea     rcx, [rax+1]
0x180078aa5  cmp     rcx, rax
0x180078aa8  jb      short loc_180078B0C
0x180078aaa  lea     rdx, [rsi+rcx]
0x180078aae  cmp     rdx, rsi
0x180078ab1  jb      short loc_180078AF4
0x180078ab3  mov     [rsp+140h+var_110], r12d
0x180078ab8  add     rdi, 10h
0x180078abc  mov     rsi, rdx
0x180078abf  cmp     rdi, r15
0x180078ac2  jnz     short loc_180078A70
0x180078ac4  lea     rcx, [rdx+1]
0x180078ac8  or      r9, 0FFFFFFFFFFFFFFFFh
0x180078acc  cmp     rcx, rdx
0x180078acf  cmovnb  r9, rcx
0x180078ad3  sbb     eax, eax
0x180078ad5  and     eax, 80070216h
0x180078ada  mov     r14d, eax
0x180078add  mov     [rbp+40h+cb], r9
0x180078ae1  mov     [rsp+140h+var_110], eax
0x180078ae5  cmp     rcx, rdx
0x180078ae8  jnb     short loc_180078B2E
0x180078aea  mov     edx, 7C3h
0x180078aef  jmp     loc_180078A03
0x180078af4  mov     r14d, 80070216h
0x180078afa  mov     [rsp+140h+var_110], r14d
0x180078aff  mov     r9d, r14d
0x180078b02  mov     edx, 7BCh
0x180078b07  jmp     loc_180078A06
0x180078b0c  mov     r14d, 80070216h
0x180078b12  mov     [rsp+140h+var_110], r14d
0x180078b17  mov     r9d, r14d
0x180078b1a  mov     edx, 7BBh
0x180078b1f  jmp     loc_180078A06
0x180078b24  mov     edx, 7B9h
0x180078b29  jmp     loc_180078A03
0x180078b2e  lea     r8, [rbp+40h+cb]; unsigned __int64 *
0x180078b32  mov     edx, 2; unsigned __int64
0x180078b37  mov     rcx, r9; unsigned __int64
0x180078b3a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180078b3f  mov     r14d, eax
0x180078b42  mov     [rsp+140h+var_110], eax
0x180078b46  test    eax, eax
0x180078b48  jns     short loc_180078B54
0x180078b4a  mov     edx, 7C4h
0x180078b4f  jmp     loc_180078A03
0x180078b54  mov     rcx, [rbp+40h+cb]; cb
0x180078b58  call    cs:__imp_CoTaskMemAlloc
0x180078b5e  mov     rsi, rax
0x180078b61  mov     [rsp+140h+var_100], rax
0x180078b66  mov     rdi, [rsp+140h+var_D8]
0x180078b6b  test    rax, rax
0x180078b6e  jz      loc_180078D47
0x180078b74  mov     r12, [r13+0]
0x180078b78  mov     r13, [r13+8]
0x180078b7c  mov     r15, rax
0x180078b7f  jmp     short loc_180078BD3
0x180078b81  mov     [rsp+140h+Src], 0
0x180078b8a  lea     rdx, [rsp+140h+Src]; unsigned __int16 **
0x180078b8f  mov     rcx, [r12]; this
0x180078b93  call    ?GetBaseHexByteString@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAPEBG@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::GetBaseHexByteString(ushort const * *)
0x180078b98  mov     r14d, eax
0x180078b9b  mov     [rsp+140h+var_110], eax
0x180078b9f  xor     eax, eax
0x180078ba1  test    r14d, r14d
0x180078ba4  js      short loc_180078C1A
0x180078ba6  mov     rdx, [rsp+140h+Src]; Src
0x180078bab  or      r14, 0FFFFFFFFFFFFFFFFh
0x180078baf  inc     r14
0x180078bb2  cmp     [rdx+r14*2], ax
0x180078bb7  jnz     short loc_180078BAF
0x180078bb9  lea     r14, ds:2[r14*2]
0x180078bc1  mov     r8, r14; Size
0x180078bc4  mov     rcx, r15; void *
0x180078bc7  call    memcpy_0
0x180078bcc  add     r15, r14
0x180078bcf  add     r12, 10h
0x180078bd3  cmp     r12, r13
0x180078bd6  jnz     short loc_180078B81
0x180078bd8  xor     r12d, r12d
0x180078bdb  mov     [r15], r12w
0x180078bdf  mov     dword ptr [rsp+140h+Src], r12d
0x180078be4  lea     rdx, [rsp+140h+Src]; unsigned int *
0x180078be9  mov     rcx, [rbp+40h+cb]; unsigned __int64
0x180078bed  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180078bf2  mov     r14d, eax
0x180078bf5  mov     [rsp+140h+var_110], eax
0x180078bf9  test    eax, eax
0x180078bfb  jns     short loc_180078C59
0x180078bfd  mov     rcx, [rbp+48h]; this
0x180078c01  mov     r9d, eax; char *
0x180078c04  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180078c0b  mov     edx, 7DCh; void *
0x180078c10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078c15  jmp     loc_180078D52
0x180078c1a  mov     rcx, [rbp+48h]; this
0x180078c1e  mov     r9d, r14d; char *
0x180078c21  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180078c28  mov     edx, 7D3h; void *
0x180078c2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078c32  nop
0x180078c33  lea     rcx, [rsp+140h+var_100]
0x180078c38  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180078c3d  nop
0x180078c3e  xor     esi, esi
0x180078c40  test    rdi, rdi
0x180078c43  jz      short loc_180078C4F
0x180078c45  mov     rcx, rdi; string
0x180078c48  call    cs:__imp_WindowsDeleteString
0x180078c4e  nop
0x180078c4f  mov     [rsp+140h+var_E0], sil
0x180078c54  jmp     loc_180078D71
  ... truncated ...
```
