# Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::EnumerateAllObjectIdsFromFilesForType(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,HSTRING__ * const,std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>,std::allocator<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>>> &)

- ea: `0x180076320`
- end: `0x180076a35`
- name: `?EnumerateAllObjectIdsFromFilesForType@StoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@KAJW4StoredObjectType@23456@QEAUHSTRING__@@AEAV?$vector@V?$shared_ptr@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@V?$allocator@V?$shared_ptr@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@2@@std@@@Z`
- size: `1813`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005a898`
- `0x18005a8ec`

## callees

- `0x18000a5d0`
- `0x18000bd40`
- `0x18001a510`
- `0x18002d940`
- `0x1800337b0`
- `0x180034e8c`
- `0x180037174`
- `0x1800372d0`
- `0x1800454f0`
- `0x180045a04`
- `0x180047294`
- `0x180048694`
- `0x180049a54`
- `0x18004d328`
- `0x180052698`
- `0x180052dc8`
- `0x180053608`
- `0x180053718`
- `0x180057a94`
- `0x18005fd50`
- `0x1800700e0`
- `0x180076320`
- `0x18007f4cc`
- `0x18007ffe0`
- `0x18008e690`
- `0x18008f234`
- `0x180091540`
- `0x18009942c`
- `0x18010bf74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007665b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800768a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007665b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800768a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007636a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800766eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800767b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007681d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007636a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800766eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800767b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007681d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007688a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076937`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076981`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007688a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076937`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076981`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800766c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18007673c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800766c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18007673c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180076784`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180076784`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007657a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007657a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180076423`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180076545`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180076423`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180076545`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800766f8`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800766f8`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180076897`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180076897`
- `bcrypt!BCryptHashData` at `0x1800764f1`
- `bcrypt!BCryptHashData` at `0x1800764f1`
- `bcrypt!BCryptCreateHash` at `0x1800764a0`
- `bcrypt!BCryptCreateHash` at `0x1800764a0`
- `bcrypt!BCryptFinishHash` at `0x180076567`
- `bcrypt!BCryptFinishHash` at `0x180076567`
- `bcrypt!BCryptGetProperty` at `0x180076533`
- `bcrypt!BCryptGetProperty` at `0x180076533`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800765f7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800765f7`

## string_xrefs

- `0x1800763ce`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180076431`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::EnumerateAllObjectIdsFromFilesForType(
        int a1,
        HSTRING a2,
        __int64 a3)
{
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  int v8; // eax
  int StoredObjectInfo; // ebx
  __int64 v10; // rdx
  unsigned int v11; // ebx
  HLOCAL v12; // rax
  HLOCAL v13; // r14
  NTSTATUS v14; // ebx
  NTSTATUS Property; // ebx
  UCHAR *v16; // rax
  UCHAR *v17; // rdi
  NTSTATUS v18; // eax
  int IsRegisteredForUser; // eax
  __int64 v20; // rdx
  signed int LastError; // eax
  signed int v22; // eax
  PCWSTR v23; // rbx
  UINT32 StringLen; // eax
  UINT32 v25; // r12d
  const WCHAR *v26; // rax
  HANDLE FirstFileW; // rdi
  UINT32 v28; // ebx
  UINT32 v29; // ebx
  HRESULT v30; // eax
  int v31; // eax
  HSTRING v32; // rbx
  const unsigned __int16 *v33; // rax
  unsigned int v34; // r8d
  int v35; // r15d
  int v36; // r14d
  signed int v37; // eax
  __int64 v38; // rdx
  SIZE_T *pbSecret; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v41; // [rsp+40h] [rbp-C0h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+48h] [rbp-B8h] BYREF
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR StringRawBuffer; // [rsp+58h] [rbp-A8h] BYREF
  SIZE_T uBytes; // [rsp+60h] [rbp-A0h] BYREF
  ULONG pcbResult[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v47; // [rsp+70h] [rbp-90h] BYREF
  __int64 v48; // [rsp+80h] [rbp-80h]
  UCHAR *v49; // [rsp+88h] [rbp-78h] BYREF
  int v50; // [rsp+90h] [rbp-70h]
  __int128 v51; // [rsp+98h] [rbp-68h]
  __int64 v52; // [rsp+A8h] [rbp-58h]
  __int64 v53; // [rsp+B0h] [rbp-50h]
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+C0h] [rbp-40h] BYREF
  char v56; // [rsp+C8h] [rbp-38h]
  HSTRING v57[5]; // [rsp+D8h] [rbp-28h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+298h]

  v53 = a3;
  if ( (unsigned int)dword_180175000 > 4 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    LODWORD(uBytes) = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v5,
      (unsigned int)byte_180159DC1,
      v6,
      v7,
      (__int64)&uBytes,
      (__int64)&StringRawBuffer);
  }
  StringRawBuffer = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v41 = 2;
  v8 = ULongLongMult(2u, 2u, &v41);
  StoredObjectInfo = v8;
  if ( v8 < 0 )
  {
    v10 = 258;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)(unsigned int)v8,
      (int)pbSecret);
LABEL_36:
    v20 = 731;
    goto LABEL_75;
  }
  LODWORD(uBytes) = 0;
  v8 = ULongLongToULong(v41, (unsigned int *)&uBytes);
  StoredObjectInfo = v8;
  if ( v8 < 0 )
  {
    v10 = 260;
    goto LABEL_5;
  }
  v11 = uBytes;
  v12 = LocalAlloc(0x40u, (unsigned int)uBytes);
  v13 = v12;
  v41 = (unsigned __int64)v12;
  if ( v12 )
  {
    if ( memcpy_s_0(v12, v11, L"*", v11) )
    {
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v41);
      StoredObjectInfo = -2147418113;
      goto LABEL_36;
    }
    hHash = 0;
    string = (HSTRING)&hHash;
    phHash = 0;
    v56 = 1;
    v14 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, &phHash, 0, 0, 0, 0, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&string);
    if ( v14 >= 0 )
    {
      Property = BCryptHashData(hHash, (PUCHAR)L"*", uBytes, 0);
      if ( Property
        || (*(_DWORD *)pbOutput = 0,
            pcbResult[0] = 0,
            (Property = BCryptGetProperty(hHash, L"HashDigestLength", pbOutput, 4u, pcbResult, 0)) != 0) )
      {
        StoredObjectInfo = Property | 0x10000000;
      }
      else
      {
        v16 = (UCHAR *)LocalAlloc(0x40u, *(unsigned int *)pbOutput);
        v17 = v16;
        if ( v16 )
        {
          v18 = BCryptFinishHash(hHash, v16, *(ULONG *)pbOutput, 0);
          if ( !v18 )
          {
            Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v49);
            v49 = v17;
            v50 = *(_DWORD *)pbOutput;
            v41 = 0;
            *(_QWORD *)&v51 = v13;
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v41);
            goto LABEL_21;
          }
          StoredObjectInfo = v18 | 0x10000000;
          LocalFree(v17);
        }
        else
        {
          LastError = GetLastError();
          StoredObjectInfo = LastError;
          if ( LastError > 0 )
            StoredObjectInfo = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
    else
    {
      StoredObjectInfo = wil::details::in1diag3::Return_NtStatus(
                           retaddr,
                           (void *)0x116,
                           (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
                           (const char *)(unsigned int)v14,
                           (int)pbSecret);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
  }
  else
  {
    v22 = GetLastError();
    StoredObjectInfo = v22;
    if ( v22 > 0 )
      StoredObjectInfo = (unsigned __int16)v22 | 0x80070000;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v41);
  if ( StoredObjectInfo < 0 )
    goto LABEL_36;
LABEL_21:
  StoredObjectInfo = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetStoredObjectInfo(
                       a1,
                       (unsigned int)&v49,
                       (_DWORD)a2,
                       (unsigned int)&StringRawBuffer,
                       1,
                       0);
  if ( StoredObjectInfo == -2147024894 )
  {
    if ( a1 )
      goto LABEL_30;
    if ( !(unsigned __int8)IsUMgrOpenProcessHandleForAccessPresent() )
      goto LABEL_30;
    v41 = 0;
    if ( (int)UMgrQueryUserContext(0, &v41) < 0 || !v41 )
      goto LABEL_30;
    IsRegisteredForUser = TbEnsurePfnIsRegisteredForUser(v41, a2);
    if ( IsRegisteredForUser < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2EC,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
        (const char *)(unsigned int)IsRegisteredForUser,
        (int)pbSecret);
    StoredObjectInfo = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetStoredObjectInfo(
                         0,
                         (unsigned int)&v49,
                         (_DWORD)a2,
                         (unsigned int)&StringRawBuffer,
                         1,
                         0);
  }
  if ( StoredObjectInfo < 0 )
  {
LABEL_30:
    v20 = 755;
LABEL_75:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)(unsigned int)StoredObjectInfo,
      (int)pbSecret);
    goto LABEL_76;
  }
  v23 = StringRawBuffer;
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)&string,
    *((const unsigned __int16 **)StringRawBuffer + 2));
  StringLen = WindowsGetStringLen(string);
  v25 = StringLen + 1;
  if ( StringLen + 1 < StringLen )
  {
    StoredObjectInfo = -2147024362;
    v20 = 759;
    goto LABEL_75;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v26 = WindowsGetStringRawBuffer(*((HSTRING *)v23 + 5), 0);
  FirstFileW = FindFirstFileW(v26, &FindFileData);
  v41 = (unsigned __int64)FirstFileW;
  v47 = 0;
  v48 = 0;
  if ( FirstFileW != (HANDLE)-1LL )
  {
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        Windows::Internal::StringReference::_ConstructorHelper(
          (Windows::Internal::StringReference *)v57,
          FindFileData.cFileName);
        v28 = WindowsGetStringLen(v57[0]);
        if ( v28 < v25 )
        {
          StoredObjectInfo = -2147024362;
          v38 = 782;
          goto LABEL_63;
        }
        v29 = v28 - v25;
        if ( v29 )
        {
          hHash = 0;
          Windows::Internal::StringReference::_ConstructorHelper(
            (Windows::Internal::StringReference *)v57,
            FindFileData.cFileName);
          *(_QWORD *)pcbResult = 0;
          v30 = WindowsSubstringWithSpecifiedLength(v57[0], 0, v29, (HSTRING *)pcbResult);
          v31 = Windows::Internal::String::FreeAndAssignOnSuccess(v30, *(HSTRING *)pcbResult, (HSTRING *)&hHash);
          StoredObjectInfo = v31;
          if ( v31 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x314,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
              (const char *)(unsigned int)v31,
              (int)pbSecret);
            if ( hHash )
              WindowsDeleteString((HSTRING)hHash);
            goto LABEL_64;
          }
          std::make_shared<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId,>(&string);
          v32 = (HSTRING)hHash;
          v33 = WindowsGetStringRawBuffer((HSTRING)hHash, 0);
          v35 = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromCryptString(
                  (Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)string,
                  v33,
                  v34);
          if ( v35 >= 0 )
          {
            if ( *((_QWORD *)&v47 + 1) == v48 )
            {
              std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>>::_Emplace_reallocate<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId> const &>(
                &v47,
                *((_QWORD *)&v47 + 1),
                &string);
            }
            else
            {
              std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>(
                *((_QWORD *)&v47 + 1),
                &string);
              *((_QWORD *)&v47 + 1) += 16LL;
            }
          }
          if ( (unsigned int)dword_180175000 > 5 )
          {
            pcbResult[0] = v35;
            hHash = FindFileData.cFileName;
            uBytes = (SIZE_T)WindowsGetStringRawBuffer(a2, 0);
            pbSecret = &uBytes;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              &dword_180175000,
              &word_180159D6E,
              0);
          }
          v36 = 0;
          if ( v35 != -2147024883 )
            v36 = v35;
          if ( v36 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x329,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
              (const char *)(unsigned int)v36,
              (int)pbSecret);
            if ( phHash )
              std::_Ref_count_base::_Decref((std::_Ref_count_base *)phHash);
            if ( v32 )
              WindowsDeleteString(v32);
            std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>>::_Tidy(&v47);
            std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::FileSearchHandleDeleter>::~unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::FileSearchHandleDeleter>(&v41);
            StoredObjectInfo = v36;
            goto LABEL_76;
          }
          if ( phHash )
            std::_Ref_count_base::_Decref((std::_Ref_count_base *)phHash);
          if ( v32 )
            WindowsDeleteString(v32);
        }
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
  }
  v37 = GetLastError();
  StoredObjectInfo = v37;
  if ( ((v37 - 2) & 0xFFFFFFEE) == 0 && v37 != 19 )
    goto LABEL_73;
  if ( v37 > 0 )
    StoredObjectInfo = (unsigned __int16)v37 | 0x80070000;
  if ( StoredObjectInfo >= 0 )
  {
LABEL_73:
    std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>>::swap(
      &v47,
      v53);
    std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>>::_Tidy(&v47);
    std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::FileSearchHandleDeleter>::~unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::FileSearchHandleDeleter>(&v41);
    Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v49);
    std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache>(&StringRawBuffer);
    return 0;
  }
  v38 = 829;
LABEL_63:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v38,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
    (const char *)(unsigned int)StoredObjectInfo,
    (int)pbSecret);
LABEL_64:
  std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>>::_Tidy(&v47);
  std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::FileSearchHandleDeleter>::~unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::FileSearchHandleDeleter>(&v41);
LABEL_76:
  Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v49);
  std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache>(&StringRawBuffer);
  return (unsigned int)StoredObjectInfo;
}

```

## disassembly

```asm
0x180076320  mov     [rsp-8+arg_18], rbx
0x180076325  push    rbp
0x180076326  push    rsi
0x180076327  push    rdi
0x180076328  push    r12
0x18007632a  push    r13
0x18007632c  push    r14
0x18007632e  push    r15
0x180076330  lea     rbp, [rsp-260h]
0x180076338  sub     rsp, 360h
0x18007633f  mov     rax, cs:__security_cookie
0x180076346  xor     rax, rsp
0x180076349  mov     [rbp+290h+var_40], rax
0x180076350  mov     [rbp+290h+var_2E0], r8
0x180076354  mov     r13, rdx
0x180076357  mov     r15d, ecx
0x18007635a  mov     eax, cs:dword_180175000
0x180076360  cmp     eax, 4
0x180076363  jbe     short loc_18007639A
0x180076365  xor     edx, edx; length
0x180076367  mov     rcx, r13; string
0x18007636a  call    cs:__imp_WindowsGetStringRawBuffer
0x180076370  mov     [rsp+390h+var_338], rax
0x180076375  mov     dword ptr [rsp+390h+uBytes], r15d
0x18007637a  lea     rax, [rsp+390h+var_338]
0x18007637f  mov     qword ptr [rsp+390h+cbSecret], rax
0x180076384  lea     rax, [rsp+390h+uBytes]
0x180076389  mov     [rsp+390h+pbSecret], rax; int
0x18007638e  lea     rdx, byte_180159DC1
0x180076395  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18007639a  xor     r12d, r12d
0x18007639d  mov     [rsp+390h+var_338], r12
0x1800763a2  mov     [rbp+290h+var_308], r12
0x1800763a6  mov     [rbp+290h+var_300], r12d
0x1800763aa  xorps   xmm0, xmm0
0x1800763ad  movdqu  [rbp+290h+var_2F8], xmm0
0x1800763b2  mov     [rbp+290h+var_2E8], r12
0x1800763b6  lea     ecx, [r12+2]; unsigned __int64
0x1800763bb  mov     [rsp+390h+var_350], rcx
0x1800763c0  lea     r8, [rsp+390h+var_350]; unsigned __int64 *
0x1800763c5  mov     edx, ecx; unsigned __int64
0x1800763c7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800763cc  mov     ebx, eax
0x1800763ce  lea     rsi, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800763d5  test    eax, eax
0x1800763d7  jns     short loc_1800763F5
0x1800763d9  mov     edx, 102h; void *
0x1800763de  mov     r8, rsi; unsigned int
0x1800763e1  mov     r9d, eax; char *
0x1800763e4  mov     rcx, [rbp+298h]; this
0x1800763eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800763f0  jmp     loc_1800766A0
0x1800763f5  mov     dword ptr [rsp+390h+uBytes], r12d
0x1800763fa  lea     rdx, [rsp+390h+uBytes]; unsigned int *
0x1800763ff  mov     rcx, [rsp+390h+var_350]; unsigned __int64
0x180076404  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180076409  mov     ebx, eax
0x18007640b  test    eax, eax
0x18007640d  jns     short loc_180076416
0x18007640f  mov     edx, 104h
0x180076414  jmp     short loc_1800763DE
0x180076416  mov     ebx, dword ptr [rsp+390h+uBytes]
0x18007641a  mov     edx, ebx; uBytes
0x18007641c  mov     edi, 40h ; '@'
0x180076421  mov     ecx, edi; uFlags
0x180076423  call    cs:__imp_LocalAlloc
0x180076429  mov     r14, rax
0x18007642c  mov     [rsp+390h+var_350], rax
0x180076431  lea     rsi, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180076438  test    rax, rax
0x18007643b  jz      loc_180076679
0x180076441  mov     r9d, ebx; SourceSize
0x180076444  lea     r8, pbInput; "*"
0x18007644b  mov     edx, ebx; DestinationSize
0x18007644d  mov     rcx, rax; Destination
0x180076450  call    memcpy_s_0
0x180076455  test    eax, eax
0x180076457  jz      short loc_18007646D
0x180076459  lea     rcx, [rsp+390h+var_350]
0x18007645e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180076463  mov     ebx, 8000FFFFh
0x180076468  jmp     loc_1800766A0
0x18007646d  mov     [rsp+390h+hHash], r12
0x180076472  lea     rax, [rsp+390h+hHash]
0x180076477  mov     [rbp+290h+string], rax
0x18007647b  mov     [rbp+290h+phHash], r12
0x18007647f  mov     [rbp+290h+var_2C8], 1
0x180076483  mov     [rsp+390h+dwFlags], r12d; dwFlags
0x180076488  mov     [rsp+390h+cbSecret], r12d; cbSecret
0x18007648d  mov     [rsp+390h+pbSecret], r12; int
0x180076492  xor     r9d, r9d; cbHashObject
0x180076495  xor     r8d, r8d; pbHashObject
0x180076498  lea     rdx, [rbp+290h+phHash]; phHash
0x18007649c  lea     ecx, [r9+31h]; hAlgorithm
0x1800764a0  call    cs:__imp_BCryptCreateHash
0x1800764a6  mov     ebx, eax
0x1800764a8  lea     rcx, [rbp+290h+string]
0x1800764ac  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1800764b1  test    ebx, ebx
0x1800764b3  jns     short loc_1800764DD
0x1800764b5  mov     rcx, [rbp+298h]; this
0x1800764bc  mov     r9d, ebx; char *
0x1800764bf  mov     r8, rsi; unsigned int
0x1800764c2  mov     edx, 116h; void *
0x1800764c7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800764cc  mov     ebx, eax
0x1800764ce  lea     rcx, [rsp+390h+hHash]
0x1800764d3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800764d8  jmp     loc_18007668E
0x1800764dd  xor     r9d, r9d; dwFlags
0x1800764e0  mov     r8d, dword ptr [rsp+390h+uBytes]; cbInput
0x1800764e5  lea     rdx, pbInput; "*"
0x1800764ec  mov     rcx, [rsp+390h+hHash]; hHash
0x1800764f1  call    cs:__imp_BCryptHashData
0x1800764f7  mov     ebx, eax
0x1800764f9  test    eax, eax
0x1800764fb  jz      short loc_180076503
0x1800764fd  bts     ebx, 1Ch
0x180076501  jmp     short loc_1800764CE
0x180076503  mov     dword ptr [rsp+390h+pbOutput], r12d
0x180076508  mov     [rsp+390h+pcbResult], r12d
0x18007650d  mov     [rsp+390h+cbSecret], r12d; dwFlags
0x180076512  lea     rax, [rsp+390h+pcbResult]
0x180076517  mov     [rsp+390h+pbSecret], rax; pcbResult
0x18007651c  mov     r9d, 4; cbOutput
0x180076522  lea     r8, [rsp+390h+pbOutput]; pbOutput
0x180076527  lea     rdx, pszProperty; "HashDigestLength"
0x18007652e  mov     rcx, [rsp+390h+hHash]; hObject
0x180076533  call    cs:__imp_BCryptGetProperty
0x180076539  mov     ebx, eax
0x18007653b  test    eax, eax
0x18007653d  jnz     short loc_1800764FD
0x18007653f  mov     edx, dword ptr [rsp+390h+pbOutput]; uBytes
0x180076543  mov     ecx, edi; uFlags
0x180076545  call    cs:__imp_LocalAlloc
0x18007654b  mov     rdi, rax
0x18007654e  test    rax, rax
0x180076551  jz      loc_18007665B
0x180076557  xor     r9d, r9d; dwFlags
0x18007655a  mov     r8d, dword ptr [rsp+390h+pbOutput]; cbOutput
0x18007655f  mov     rdx, rax; pbOutput
0x180076562  mov     rcx, [rsp+390h+hHash]; hHash
0x180076567  call    cs:__imp_BCryptFinishHash
0x18007656d  mov     ebx, eax
0x18007656f  test    eax, eax
0x180076571  jz      short loc_180076585
0x180076573  bts     ebx, 1Ch
0x180076577  mov     rcx, rdi; hMem
0x18007657a  call    cs:__imp_LocalFree
0x180076580  jmp     loc_1800764CE
0x180076585  lea     rcx, [rbp+290h+var_308]; this
0x180076589  call    ?InternalRelease@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@AEAAXXZ; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease(void)
0x18007658e  mov     [rbp+290h+var_308], rdi
0x180076592  mov     eax, dword ptr [rsp+390h+pbOutput]
0x180076596  mov     [rbp+290h+var_300], eax
0x180076599  mov     [rsp+390h+var_350], r12
0x18007659e  mov     qword ptr [rbp+290h+var_2F8], r14
0x1800765a2  lea     rcx, [rsp+390h+hHash]
0x1800765a7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800765ac  lea     rcx, [rsp+390h+var_350]
0x1800765b1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800765b6  mov     byte ptr [rsp+390h+cbSecret], r12b
0x1800765bb  mov     byte ptr [rsp+390h+pbSecret], 1; int
0x1800765c0  lea     r9, [rsp+390h+var_338]
0x1800765c5  mov     r8, r13
0x1800765c8  lea     rdx, [rbp+290h+var_308]
0x1800765cc  mov     ecx, r15d
0x1800765cf  call    ?GetStoredObjectInfo@StoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@SAJW4StoredObjectType@23456@AEAVStoredObjectId@23456@QEAUHSTRING__@@AEAV?$unique_ptr@VStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@U?$default_delete@VStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@std@@_N4@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetStoredObjectInfo(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,HSTRING__ * const,std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo> &,bool,bool)
0x1800765d4  mov     ebx, eax
0x1800765d6  cmp     eax, 80070002h
0x1800765db  jnz     short loc_18007664D
0x1800765dd  test    r15d, r15d
0x1800765e0  jnz     short loc_180076651
0x1800765e2  call    IsUMgrOpenProcessHandleForAccessPresent
0x1800765e7  test    al, al
0x1800765e9  jz      short loc_180076651
0x1800765eb  mov     [rsp+390h+var_350], r12
0x1800765f0  lea     rdx, [rsp+390h+var_350]
0x1800765f5  xor     ecx, ecx
0x1800765f7  call    cs:__imp_UMgrQueryUserContext
0x1800765fd  test    eax, eax
0x1800765ff  js      short loc_180076651
0x180076601  mov     rcx, [rsp+390h+var_350]; unsigned __int64
0x180076606  test    rcx, rcx
0x180076609  jz      short loc_180076651
0x18007660b  mov     rdx, r13; HSTRING
0x18007660e  call    ?TbEnsurePfnIsRegisteredForUser@@YAJ_KPEAUHSTRING__@@@Z; TbEnsurePfnIsRegisteredForUser(unsigned __int64,HSTRING__ *)
0x180076613  mov     rcx, [rbp+298h]; this
0x18007661a  test    eax, eax
0x18007661c  jns     short loc_18007662E
0x18007661e  mov     r9d, eax; char *
0x180076621  mov     r8, rsi; unsigned int
0x180076624  mov     edx, 2ECh; void *
0x180076629  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007662e  mov     byte ptr [rsp+390h+cbSecret], r12b
0x180076633  mov     byte ptr [rsp+390h+pbSecret], 1; int
0x180076638  lea     r9, [rsp+390h+var_338]
0x18007663d  mov     r8, r13
0x180076640  lea     rdx, [rbp+290h+var_308]
0x180076644  xor     ecx, ecx
0x180076646  call    ?GetStoredObjectInfo@StoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@SAJW4StoredObjectType@23456@AEAVStoredObjectId@23456@QEAUHSTRING__@@AEAV?$unique_ptr@VStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@U?$default_delete@VStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@std@@_N4@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetStoredObjectInfo(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,HSTRING__ * const,std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo> &,bool,bool)
0x18007664b  mov     ebx, eax
0x18007664d  test    ebx, ebx
0x18007664f  jns     short loc_1800766AA
0x180076651  mov     edx, 2F3h
0x180076656  jmp     loc_1800769E2
0x18007665b  call    cs:__imp_GetLastError
0x180076661  mov     ebx, eax
0x180076663  test    eax, eax
0x180076665  jle     loc_1800764CE
0x18007666b  movzx   ebx, ax
0x18007666e  or      ebx, 80070000h
0x180076674  jmp     loc_1800764CE
0x180076679  call    cs:__imp_GetLastError
0x18007667f  mov     ebx, eax
0x180076681  test    eax, eax
0x180076683  jle     short loc_18007668E
0x180076685  movzx   ebx, ax
0x180076688  or      ebx, 80070000h
0x18007668e  lea     rcx, [rsp+390h+var_350]
0x180076693  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180076698  test    ebx, ebx
0x18007669a  jns     loc_1800765B6
0x1800766a0  mov     edx, 2DBh
0x1800766a5  jmp     loc_1800769E2
0x1800766aa  mov     rbx, [rsp+390h+var_338]
0x1800766af  mov     rdx, [rbx+10h]; unsigned __int16 *
0x1800766b3  lea     rcx, [rbp+290h+string]; this
0x1800766b7  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800766bc  mov     rcx, [rbp+290h+string]; string
0x1800766c0  call    cs:__imp_WindowsGetStringLen
0x1800766c6  lea     r12d, [rax+1]
0x1800766ca  cmp     r12d, eax
0x1800766cd  jb      loc_1800769D8
0x1800766d3  xor     edx, edx; Val
0x1800766d5  mov     r8d, 250h; Size
0x1800766db  lea     rcx, [rbp+290h+FindFileData]; void *
0x1800766df  call    memset_0
0x1800766e4  nop
0x1800766e5  xor     edx, edx; length
0x1800766e7  mov     rcx, [rbx+28h]; string
0x1800766eb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800766f1  lea     rdx, [rbp+290h+FindFileData]; lpFindFileData
0x1800766f5  mov     rcx, rax; lpFileName
0x1800766f8  call    cs:__imp_FindFirstFileW
0x1800766fe  mov     rdi, rax
0x180076701  mov     [rsp+390h+var_350], rax
0x180076706  xorps   xmm0, xmm0
0x180076709  movdqu  [rsp+390h+var_320], xmm0
0x18007670f  mov     [rbp+290h+var_310], 0
0x180076717  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007671b  jz      loc_1800768A5
0x180076721  test    byte ptr [rbp+290h+FindFileData.dwFileAttributes], 10h
0x180076725  jnz     loc_180076890
0x18007672b  lea     rdx, [rbp+290h+FindFileData.cFileName]; unsigned __int16 *
0x18007672f  lea     rcx, [rbp+290h+var_2B8]; this
0x180076733  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180076738  mov     rcx, [rbp+290h+var_2B8]; string
0x18007673c  call    cs:__imp_WindowsGetStringLen
0x180076742  mov     ebx, eax
0x180076744  cmp     eax, r12d
0x180076747  jb      loc_18007698C
0x18007674d  sub     ebx, r12d
0x180076750  jz      loc_180076890
0x180076756  mov     [rsp+390h+hHash], 0
0x18007675f  lea     rdx, [rbp+290h+FindFileData.cFileName]; unsigned __int16 *
0x180076763  lea     rcx, [rbp+290h+var_2B8]; this
0x180076767  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18007676c  nop
0x18007676d  mov     qword ptr [rsp+390h+pcbResult], 0
0x180076776  lea     r9, [rsp+390h+pcbResult]; newString
0x18007677b  mov     r8d, ebx; length
0x18007677e  xor     edx, edx; startIndex
0x180076780  mov     rcx, [rbp+290h+var_2B8]; string
0x180076784  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x18007678a  lea     r8, [rsp+390h+hHash]; HSTRING *
0x18007678f  mov     rdx, qword ptr [rsp+390h+pcbResult]; HSTRING
0x180076794  mov     ecx, eax; int
0x180076796  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x18007679b  mov     ebx, eax
0x18007679d  test    eax, eax
0x18007679f  js      loc_18007695B
0x1800767a5  lea     rcx, [rbp+290h+string]
0x1800767a9  call    ??$make_shared@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@$$V@std@@YA?AV?$shared_ptr@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@0@XZ; std::make_shared<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId,>(void)
0x1800767ae  nop
0x1800767af  xor     edx, edx; length
0x1800767b1  mov     rbx, [rsp+390h+hHash]
0x1800767b6  mov     rcx, rbx; string
0x1800767b9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800767bf  mov     rdx, rax; unsigned __int16 *
0x1800767c2  mov     rcx, [rbp+290h+string]; this
0x1800767c6  call    ?InitializeFromCryptString@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@AEAAJPEBGK@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromCryptString(ushort const *,ulong)
0x1800767cb  mov     r15d, eax
0x1800767ce  test    eax, eax
0x1800767d0  js      short loc_1800767FF
0x1800767d2  mov     rcx, qword ptr [rsp+390h+var_320+8]
0x1800767d7  cmp     rcx, [rbp+290h+var_310]
0x1800767db  jz      short loc_1800767EE
0x1800767dd  lea     rdx, [rbp+290h+string]
0x1800767e1  call    ??0?$shared_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>(std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext> const &)
  ... truncated ...
```
