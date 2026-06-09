# CalculatePairwiseId(HSTRING__ * const,HSTRING__ * const,HSTRING__ * const,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::LocalAllocDeleter> &,ulong,Windows::Internal::String &)

- ea: `0x180071b10`
- end: `0x1800722a5`
- name: `?CalculatePairwiseId@@YAJQEAUHSTRING__@@00AEAV?$unique_ptr@PEAXULocalAllocDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@KAEAVString@Internal@Windows@@@Z`
- size: `1941`
- prototype: `__int64 __usercall@<rax>(HSTRING@<rcx>, HSTRING string@<rdx>, HSTRING@<r8>, ULONG, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1800722ac`
- `0x1800724cc`

## callees

- `0x180009be0`
- `0x18000bd40`
- `0x180034e20`
- `0x1800426b0`
- `0x180044d30`
- `0x180049a54`
- `0x18006fb0c`
- `0x180071b10`
- `0x18007f4cc`
- `0x18008e690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071f7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071f7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072019`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071b8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071b9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071bac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071b8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071b9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071bac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071c6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071caa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071ced`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071d58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071d86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071dc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071e07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071e16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071e86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071e95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800720fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072109`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072178`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072186`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071c6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071caa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071ced`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071d58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071d86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071dc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071e07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071e16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071e86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071e95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800720fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072109`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072178`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072186`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180072168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180072168`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18007227c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18007227c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071d0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071d77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071e3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071eb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071fd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072053`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072066`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007206e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072076`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007207e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800720c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800720ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800720d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800720e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800720eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007212c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800721b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800721bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800721c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071d0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071d77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071e3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071eb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071fd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072053`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072066`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007206e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072076`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007207e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800720c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800720ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800720d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800720e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800720eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007212c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800721b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800721bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800721c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071f6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007200b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071f6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007200b`
- `bcrypt!BCryptHashData` at `0x180071d2c`
- `bcrypt!BCryptHashData` at `0x180071e59`
- `bcrypt!BCryptHashData` at `0x180071ed0`
- `bcrypt!BCryptHashData` at `0x180071f13`
- `bcrypt!BCryptHashData` at `0x180071d2c`
- `bcrypt!BCryptHashData` at `0x180071e59`
- `bcrypt!BCryptHashData` at `0x180071ed0`
- `bcrypt!BCryptHashData` at `0x180071f13`
- `bcrypt!BCryptCreateHash` at `0x180071c1a`
- `bcrypt!BCryptCreateHash` at `0x180071c1a`
- `bcrypt!BCryptFinishHash` at `0x180071fab`
- `bcrypt!BCryptFinishHash` at `0x180071fab`
- `bcrypt!BCryptDestroyHash` at `0x180071c5c`
- `bcrypt!BCryptDestroyHash` at `0x180071cfd`
- `bcrypt!BCryptDestroyHash` at `0x180071d68`
- `bcrypt!BCryptDestroyHash` at `0x180071e26`
- `bcrypt!BCryptDestroyHash` at `0x180071ea5`
- `bcrypt!BCryptDestroyHash` at `0x180072119`
- `bcrypt!BCryptDestroyHash` at `0x180071c5c`
- `bcrypt!BCryptDestroyHash` at `0x180071cfd`
- `bcrypt!BCryptDestroyHash` at `0x180071d68`
- `bcrypt!BCryptDestroyHash` at `0x180071e26`
- `bcrypt!BCryptDestroyHash` at `0x180071ea5`
- `bcrypt!BCryptDestroyHash` at `0x180072119`
- `bcrypt!BCryptGetProperty` at `0x180071f52`
- `bcrypt!BCryptGetProperty` at `0x180071f52`

## string_xrefs

- `0x180071c40`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180071c8f`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180071cd3`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180071d3d`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180071da9`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180071dee`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180071e6b`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180071fbc`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x1800720af`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x1800721a2`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CalculatePairwiseId(HSTRING a1, HSTRING string, HSTRING a3, PUCHAR *a4, ULONG a5, __int64 a6)
{
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  HSTRING v13; // r14
  NTSTATUS Hash; // ebx
  unsigned int v15; // ebx
  int v17; // eax
  HSTRING v18; // rbx
  int v19; // eax
  unsigned int v20; // edi
  HLOCAL v21; // rdi
  NTSTATUS v22; // eax
  int v23; // esi
  int v24; // eax
  HSTRING v25; // rdi
  __int64 v26; // rdx
  HLOCAL v27; // rsi
  NTSTATUS Property; // eax
  __int64 v29; // rdx
  unsigned int v30; // r14d
  UCHAR *v31; // rax
  UCHAR *v32; // r12
  signed int LastError; // eax
  NTSTATUS v34; // eax
  rsize_t v35; // r13
  HLOCAL v36; // rax
  void *v37; // r15
  signed int v38; // eax
  unsigned int v39; // r15d
  int BaseHexByteString; // eax
  HLOCAL v41; // rcx
  const WCHAR *v42; // rcx
  unsigned __int64 v43; // rdx
  HSTRING *v44; // r13
  int pbSecret; // [rsp+20h] [rbp-99h]
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-79h] BYREF
  ULONG cbInput; // [rsp+48h] [rbp-71h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-69h] BYREF
  HSTRING StringRawBuffer; // [rsp+58h] [rbp-61h] BYREF
  UCHAR pbOutput[4]; // [rsp+60h] [rbp-59h] BYREF
  ULONG pcbResult; // [rsp+64h] [rbp-55h] BYREF
  HSTRING stringa; // [rsp+68h] [rbp-51h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v54; // [rsp+80h] [rbp-39h] BYREF
  HLOCAL v55[2]; // [rsp+90h] [rbp-29h]
  HLOCAL p_cbInput; // [rsp+A0h] [rbp-19h]
  __int64 v57; // [rsp+A8h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+4Fh]

  *(_QWORD *)&EventDescriptor.Id = a6;
  if ( !a1 || !a3 || !string || !*a4 || !a5 )
  {
    v39 = -2147024809;
    if ( (unsigned int)dword_180175000 > 2 )
    {
      cbInput = -2147024809;
      p_cbInput = &cbInput;
      v57 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      v54.Ptr = (ULONGLONG)off_180175008;
      v54.Size = *(unsigned __int16 *)off_180175008;
      v54.Reserved = 2;
      v55[0] = byte_180158D2B;
      v55[1] = (HLOCAL)0x10000002ELL;
      pcbResult = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v54);
    }
    return v39;
  }
  if ( (unsigned int)dword_180175000 > 5 )
  {
    StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(a3, 0);
    stringa = (HSTRING)WindowsGetStringRawBuffer(a1, 0);
    hMem = (HLOCAL)WindowsGetStringRawBuffer(string, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v10,
      (unsigned int)&dword_180158CD4,
      v11,
      v12,
      (__int64)&hMem,
      (__int64)&stringa,
      (__int64)&StringRawBuffer);
  }
  v13 = 0;
  cbInput = 0;
  hMem = 0;
  hHash = 0;
  v54.Ptr = (ULONGLONG)&hHash;
  *(_QWORD *)&v54.Size = 0;
  LOBYTE(v55[0]) = 1;
  Hash = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, (BCRYPT_HASH_HANDLE *)&v54.Size, 0, 0, 0, 0, 0);
  if ( LOBYTE(v55[0]) )
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      v54.Ptr,
      *(_QWORD *)&v54.Size);
  if ( Hash < 0 )
  {
    v15 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x362,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
            (const char *)(unsigned int)Hash,
            pbSecret);
LABEL_12:
    if ( hHash )
      BCryptDestroyHash(hHash);
    return v15;
  }
  WindowsDeleteString(0);
  stringa = 0;
  v17 = Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::NormalizePFN(a1, &stringa);
  v15 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x366,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v17,
      pbSecret);
    if ( stringa )
      WindowsDeleteString(stringa);
    goto LABEL_12;
  }
  v18 = stringa;
  v19 = Sha256HashString(stringa);
  v20 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x367,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v19,
      pbSecret);
    if ( v18 )
      WindowsDeleteString(v18);
    if ( hHash )
      BCryptDestroyHash(hHash);
    if ( hMem )
      LocalFree(hMem);
    return v20;
  }
  v21 = hMem;
  v22 = BCryptHashData(hHash, (PUCHAR)hMem, cbInput, 0);
  if ( v22 < 0 )
  {
    v23 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x369,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
            (const char *)(unsigned int)v22,
            pbSecret);
LABEL_28:
    if ( v18 )
      WindowsDeleteString(v18);
    if ( hHash )
      BCryptDestroyHash(hHash);
    if ( v21 )
      LocalFree(v21);
    return (unsigned int)v23;
  }
  WindowsDeleteString(0);
  StringRawBuffer = 0;
  v24 = Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::NormalizePFN(a3, &StringRawBuffer);
  v23 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36D,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v24,
      pbSecret);
    if ( StringRawBuffer )
      WindowsDeleteString(StringRawBuffer);
    goto LABEL_28;
  }
  v25 = StringRawBuffer;
  v23 = Sha256HashString(StringRawBuffer);
  if ( v23 < 0 )
  {
    v26 = 878;
    goto LABEL_40;
  }
  v27 = hMem;
  Property = BCryptHashData(hHash, (PUCHAR)hMem, cbInput, 0);
  if ( Property >= 0 )
  {
    Property = BCryptHashData(hHash, *a4, a5, 0);
    if ( Property < 0 )
    {
      v29 = 884;
      goto LABEL_50;
    }
    v23 = Sha256HashString(string);
    if ( v23 < 0 )
    {
      v26 = 887;
LABEL_40:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v23,
        pbSecret);
      if ( v25 )
        WindowsDeleteString(v25);
      if ( v18 )
        WindowsDeleteString(v18);
      if ( hHash )
        BCryptDestroyHash(hHash);
      if ( hMem )
      {
        LocalFree(hMem);
        return (unsigned int)v23;
      }
      return (unsigned int)v23;
    }
    v27 = hMem;
    Property = BCryptHashData(hHash, (PUCHAR)hMem, cbInput, 0);
    if ( Property < 0 )
    {
      v29 = 889;
      goto LABEL_50;
    }
    *(_DWORD *)pbOutput = 0;
    pcbResult = 0;
    Property = BCryptGetProperty(hHash, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property < 0 )
    {
      v29 = 896;
      goto LABEL_50;
    }
    v31 = (UCHAR *)LocalAlloc(0x40u, *(unsigned int *)pbOutput);
    v32 = v31;
    if ( !v31 )
    {
      LastError = GetLastError();
      v30 = LastError;
      if ( LastError > 0 )
        v30 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_51;
    }
    v34 = BCryptFinishHash(hHash, v31, *(ULONG *)pbOutput, 0);
    if ( v34 < 0 )
    {
      v30 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x389,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
              (const char *)(unsigned int)v34,
              pbSecret);
      LocalFree(v32);
      goto LABEL_51;
    }
    v54.Ptr = 0;
    v54.Size = 0;
    *(_OWORD *)v55 = 0;
    p_cbInput = 0;
    v35 = *(unsigned int *)pbOutput;
    if ( (unsigned int)(*(_DWORD *)pbOutput - 1) > 0x1F )
    {
      v39 = -2147024809;
    }
    else
    {
      v36 = LocalAlloc(0x40u, *(unsigned int *)pbOutput);
      v37 = v36;
      if ( !v36 )
      {
        v38 = GetLastError();
        v39 = v38;
        if ( v38 > 0 )
          v39 = (unsigned __int16)v38 | 0x80070000;
        if ( (v39 & 0x80000000) != 0 )
          goto LABEL_101;
LABEL_82:
        StringRawBuffer = 0;
        BaseHexByteString = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::GetBaseHexByteString(
                              (Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v54,
                              (const unsigned __int16 **)&StringRawBuffer);
        v39 = BaseHexByteString;
        if ( BaseHexByteString >= 0 )
        {
          v42 = (const WCHAR *)StringRawBuffer;
          if ( StringRawBuffer )
          {
            StringRawBuffer = 0;
            v43 = -1;
            do
              ++v43;
            while ( v42[v43] );
            if ( v43 <= 0xFFFFFFFF && WindowsCreateString(v42, v43, &StringRawBuffer) >= 0 )
            {
              v13 = StringRawBuffer;
              WindowsDeleteString(0);
            }
          }
          v44 = *(HSTRING **)&EventDescriptor.Id;
          WindowsDeleteString(**(HSTRING **)&EventDescriptor.Id);
          *v44 = v13;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x393,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
            (const char *)(unsigned int)BaseHexByteString,
            pbSecret);
        }
        LocalFree((HLOCAL)v54.Ptr);
        LocalFree(v55[0]);
        LocalFree(v55[1]);
        v41 = p_cbInput;
        goto LABEL_85;
      }
      if ( !memcpy_s_0(v36, v35, v32, v35) )
      {
        LocalFree(0);
        LocalFree(0);
        LocalFree(0);
        LocalFree(0);
        v54.Ptr = (ULONGLONG)v37;
        v54.Size = v35;
        goto LABEL_82;
      }
      LocalFree(v37);
      v39 = -2147418113;
    }
LABEL_101:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x390,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)v39,
      pbSecret);
    LocalFree(0);
    LocalFree(0);
    LocalFree(0);
    v41 = 0;
LABEL_85:
    LocalFree(v41);
    LocalFree(v32);
    if ( v25 )
      WindowsDeleteString(v25);
    if ( v18 )
      WindowsDeleteString(v18);
    if ( hHash )
      BCryptDestroyHash(hHash);
    if ( v27 )
      LocalFree(v27);
    return v39;
  }
  v29 = 880;
LABEL_50:
  v30 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)v29,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
          (const char *)(unsigned int)Property,
          pbSecret);
LABEL_51:
  if ( v25 )
    WindowsDeleteString(v25);
  if ( v18 )
    WindowsDeleteString(v18);
  if ( hHash )
    BCryptDestroyHash(hHash);
  if ( v27 )
    LocalFree(v27);
  return v30;
}

```

## disassembly

```asm
0x180071b10  push    rbp
0x180071b12  push    rbx
0x180071b13  push    rsi
0x180071b14  push    rdi
0x180071b15  push    r12
0x180071b17  push    r13
0x180071b19  push    r14
0x180071b1b  push    r15
0x180071b1d  lea     rbp, [rsp-0Fh]
0x180071b22  sub     rsp, 0C8h
0x180071b29  mov     rax, cs:__security_cookie
0x180071b30  xor     rax, rsp
0x180071b33  mov     [rbp+47h+var_50], rax
0x180071b37  mov     r13, r9
0x180071b3a  mov     rsi, r8
0x180071b3d  mov     r15, rdx
0x180071b40  mov     rdi, rcx
0x180071b43  mov     rax, [rbp+47h+arg_28]
0x180071b47  mov     qword ptr [rbp+47h+EventDescriptor.Id], rax
0x180071b4b  test    rcx, rcx
0x180071b4e  jz      loc_1800721D2
0x180071b54  test    r8, r8
0x180071b57  jz      loc_1800721D2
0x180071b5d  test    rdx, rdx
0x180071b60  jz      loc_1800721D2
0x180071b66  cmp     qword ptr [r9], 0
0x180071b6a  jz      loc_1800721D2
0x180071b70  mov     r12d, [rbp+47h+arg_20]
0x180071b74  cmp     r12d, 1
0x180071b78  jb      loc_1800721D2
0x180071b7e  mov     eax, cs:dword_180175000
0x180071b84  cmp     eax, 5
0x180071b87  jbe     short loc_180071BDD
0x180071b89  xor     edx, edx; length
0x180071b8b  mov     rcx, r8; string
0x180071b8e  call    cs:__imp_WindowsGetStringRawBuffer
0x180071b94  mov     [rbp+47h+var_A8], rax
0x180071b98  xor     edx, edx; length
0x180071b9a  mov     rcx, rdi; string
0x180071b9d  call    cs:__imp_WindowsGetStringRawBuffer
0x180071ba3  mov     [rbp+47h+string], rax
0x180071ba7  xor     edx, edx; length
0x180071ba9  mov     rcx, r15; string
0x180071bac  call    cs:__imp_WindowsGetStringRawBuffer
0x180071bb2  mov     [rbp+47h+hMem], rax
0x180071bb6  lea     rax, [rbp+47h+var_A8]
0x180071bba  mov     qword ptr [rsp+100h+dwFlags], rax
0x180071bbf  lea     rax, [rbp+47h+string]
0x180071bc3  mov     qword ptr [rsp+100h+cbSecret], rax
0x180071bc8  lea     rax, [rbp+47h+hMem]
0x180071bcc  mov     [rsp+100h+pbSecret], rax
0x180071bd1  lea     rdx, dword_180158CD4
0x180071bd8  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180071bdd  xor     r14d, r14d
0x180071be0  mov     [rbp+47h+cbInput], r14d
0x180071be4  mov     [rbp+47h+hMem], r14
0x180071be8  mov     [rbp+47h+hHash], r14
0x180071bec  lea     rax, [rbp+47h+hHash]
0x180071bf0  mov     [rbp+47h+var_80], rax
0x180071bf4  mov     [rbp+47h+phHash], r14
0x180071bf8  mov     byte ptr [rbp+47h+var_70], 1
0x180071bfc  mov     [rsp+100h+dwFlags], r14d; dwFlags
0x180071c01  mov     [rsp+100h+cbSecret], r14d; cbSecret
0x180071c06  mov     [rsp+100h+pbSecret], r14; int
0x180071c0b  xor     r9d, r9d; cbHashObject
0x180071c0e  xor     r8d, r8d; pbHashObject
0x180071c11  lea     rdx, [rbp+47h+phHash]; phHash
0x180071c15  mov     ecx, 41h ; 'A'; hAlgorithm
0x180071c1a  call    cs:__imp_BCryptCreateHash
0x180071c20  mov     ebx, eax
0x180071c22  cmp     byte ptr [rbp+47h+var_70], r14b
0x180071c26  jz      short loc_180071C35
0x180071c28  mov     rdx, [rbp+47h+phHash]
0x180071c2c  mov     rcx, [rbp+47h+var_80]
0x180071c30  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180071c35  test    ebx, ebx
0x180071c37  jns     short loc_180071C6A
0x180071c39  mov     rcx, [rbp+4Fh]; this
0x180071c3d  mov     r9d, ebx; char *
0x180071c40  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180071c47  mov     edx, 362h; void *
0x180071c4c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180071c51  mov     ebx, eax
0x180071c53  mov     rcx, [rbp+47h+hHash]; hHash
0x180071c57  test    rcx, rcx
0x180071c5a  jz      short loc_180071C63
0x180071c5c  call    cs:__imp_BCryptDestroyHash
0x180071c62  nop
0x180071c63  mov     eax, ebx
0x180071c65  jmp     loc_180072285
0x180071c6a  xor     ecx, ecx; string
0x180071c6c  call    cs:__imp_WindowsDeleteString
0x180071c72  mov     [rbp+47h+string], r14
0x180071c76  lea     rdx, [rbp+47h+string]; HSTRING *
0x180071c7a  mov     rcx, rdi; HSTRING
0x180071c7d  call    ?NormalizePFN@ApplicationCallbackUri@Web@Authentication@Security@Internal@Windows@@SAJQEAUHSTRING__@@PEAPEAU7@@Z; Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::NormalizePFN(HSTRING__ * const,HSTRING__ * *)
0x180071c82  mov     ebx, eax
0x180071c84  test    eax, eax
0x180071c86  jns     short loc_180071CB2
0x180071c88  mov     rcx, [rbp+4Fh]; this
0x180071c8c  mov     r9d, eax; char *
0x180071c8f  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180071c96  mov     edx, 366h; void *
0x180071c9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071ca0  nop
0x180071ca1  mov     rcx, [rbp+47h+string]; string
0x180071ca5  test    rcx, rcx
0x180071ca8  jz      short loc_180071C53
0x180071caa  call    cs:__imp_WindowsDeleteString
0x180071cb0  jmp     short loc_180071C53
0x180071cb2  lea     r8, [rbp+47h+cbInput]
0x180071cb6  lea     rdx, [rbp+47h+hMem]
0x180071cba  mov     rbx, [rbp+47h+string]
0x180071cbe  mov     rcx, rbx; string
0x180071cc1  call    ?Sha256HashString@@YAJQEAUHSTRING__@@AEAV?$unique_ptr@PEAXULocalAllocDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@PEAK@Z; Sha256HashString(HSTRING__ * const,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::LocalAllocDeleter> &,ulong *)
0x180071cc6  mov     edi, eax
0x180071cc8  test    eax, eax
0x180071cca  jns     short loc_180071D1A
0x180071ccc  mov     rcx, [rbp+4Fh]; this
0x180071cd0  mov     r9d, eax; char *
0x180071cd3  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180071cda  mov     edx, 367h; void *
0x180071cdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071ce4  nop
0x180071ce5  test    rbx, rbx
0x180071ce8  jz      short loc_180071CF4
0x180071cea  mov     rcx, rbx; string
0x180071ced  call    cs:__imp_WindowsDeleteString
0x180071cf3  nop
0x180071cf4  mov     rcx, [rbp+47h+hHash]; hHash
0x180071cf8  test    rcx, rcx
0x180071cfb  jz      short loc_180071D04
0x180071cfd  call    cs:__imp_BCryptDestroyHash
0x180071d03  nop
0x180071d04  mov     rcx, [rbp+47h+hMem]; hMem
0x180071d08  test    rcx, rcx
0x180071d0b  jz      short loc_180071D13
0x180071d0d  call    cs:__imp_LocalFree
0x180071d13  mov     eax, edi
0x180071d15  jmp     loc_180072285
0x180071d1a  xor     r9d, r9d; dwFlags
0x180071d1d  mov     r8d, [rbp+47h+cbInput]; cbInput
0x180071d21  mov     rdi, [rbp+47h+hMem]
0x180071d25  mov     rdx, rdi; pbInput
0x180071d28  mov     rcx, [rbp+47h+hHash]; hHash
0x180071d2c  call    cs:__imp_BCryptHashData
0x180071d32  test    eax, eax
0x180071d34  jns     short loc_180071D84
0x180071d36  mov     rcx, [rbp+4Fh]; this
0x180071d3a  mov     r9d, eax; char *
0x180071d3d  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180071d44  mov     edx, 369h; void *
0x180071d49  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180071d4e  mov     esi, eax
0x180071d50  test    rbx, rbx
0x180071d53  jz      short loc_180071D5F
0x180071d55  mov     rcx, rbx; string
0x180071d58  call    cs:__imp_WindowsDeleteString
0x180071d5e  nop
0x180071d5f  mov     rcx, [rbp+47h+hHash]; hHash
0x180071d63  test    rcx, rcx
0x180071d66  jz      short loc_180071D6F
0x180071d68  call    cs:__imp_BCryptDestroyHash
0x180071d6e  nop
0x180071d6f  test    rdi, rdi
0x180071d72  jz      short loc_180071D7D
0x180071d74  mov     rcx, rdi; hMem
0x180071d77  call    cs:__imp_LocalFree
0x180071d7d  mov     eax, esi
0x180071d7f  jmp     loc_180072285
0x180071d84  xor     ecx, ecx; string
0x180071d86  call    cs:__imp_WindowsDeleteString
0x180071d8c  mov     [rbp+47h+var_A8], r14
0x180071d90  lea     rdx, [rbp+47h+var_A8]; HSTRING *
0x180071d94  mov     rcx, rsi; HSTRING
0x180071d97  call    ?NormalizePFN@ApplicationCallbackUri@Web@Authentication@Security@Internal@Windows@@SAJQEAUHSTRING__@@PEAPEAU7@@Z; Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::NormalizePFN(HSTRING__ * const,HSTRING__ * *)
0x180071d9c  mov     esi, eax
0x180071d9e  test    eax, eax
0x180071da0  jns     short loc_180071DCC
0x180071da2  mov     rcx, [rbp+4Fh]; this
0x180071da6  mov     r9d, eax; char *
0x180071da9  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180071db0  mov     edx, 36Dh; void *
0x180071db5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071dba  nop
0x180071dbb  mov     rcx, [rbp+47h+var_A8]; string
0x180071dbf  test    rcx, rcx
0x180071dc2  jz      short loc_180071D50
0x180071dc4  call    cs:__imp_WindowsDeleteString
0x180071dca  jmp     short loc_180071D50
0x180071dcc  lea     r8, [rbp+47h+cbInput]
0x180071dd0  lea     rdx, [rbp+47h+hMem]
0x180071dd4  mov     rdi, [rbp+47h+var_A8]
0x180071dd8  mov     rcx, rdi; string
0x180071ddb  call    ?Sha256HashString@@YAJQEAUHSTRING__@@AEAV?$unique_ptr@PEAXULocalAllocDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@PEAK@Z; Sha256HashString(HSTRING__ * const,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::LocalAllocDeleter> &,ulong *)
0x180071de0  mov     esi, eax
0x180071de2  test    eax, eax
0x180071de4  jns     short loc_180071E47
0x180071de6  mov     edx, 36Eh; void *
0x180071deb  mov     r9d, esi; char *
0x180071dee  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180071df5  mov     rcx, [rbp+4Fh]; this
0x180071df9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071dfe  nop
0x180071dff  test    rdi, rdi
0x180071e02  jz      short loc_180071E0E
0x180071e04  mov     rcx, rdi; string
0x180071e07  call    cs:__imp_WindowsDeleteString
0x180071e0d  nop
0x180071e0e  test    rbx, rbx
0x180071e11  jz      short loc_180071E1D
0x180071e13  mov     rcx, rbx; string
0x180071e16  call    cs:__imp_WindowsDeleteString
0x180071e1c  nop
0x180071e1d  mov     rcx, [rbp+47h+hHash]; hHash
0x180071e21  test    rcx, rcx
0x180071e24  jz      short loc_180071E2D
0x180071e26  call    cs:__imp_BCryptDestroyHash
0x180071e2c  nop
0x180071e2d  mov     rcx, [rbp+47h+hMem]; hMem
0x180071e31  test    rcx, rcx
0x180071e34  jz      loc_180071D7D
0x180071e3a  call    cs:__imp_LocalFree
0x180071e40  mov     eax, esi
0x180071e42  jmp     loc_180072285
0x180071e47  xor     r9d, r9d; dwFlags
0x180071e4a  mov     r8d, [rbp+47h+cbInput]; cbInput
0x180071e4e  mov     rsi, [rbp+47h+hMem]
0x180071e52  mov     rdx, rsi; pbInput
0x180071e55  mov     rcx, [rbp+47h+hHash]; hHash
0x180071e59  call    cs:__imp_BCryptHashData
0x180071e5f  test    eax, eax
0x180071e61  jns     short loc_180071EC2
0x180071e63  mov     edx, 370h; void *
0x180071e68  mov     r9d, eax; char *
0x180071e6b  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180071e72  mov     rcx, [rbp+4Fh]; this
0x180071e76  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180071e7b  mov     r14d, eax
0x180071e7e  test    rdi, rdi
0x180071e81  jz      short loc_180071E8D
0x180071e83  mov     rcx, rdi; string
0x180071e86  call    cs:__imp_WindowsDeleteString
0x180071e8c  nop
0x180071e8d  test    rbx, rbx
0x180071e90  jz      short loc_180071E9C
0x180071e92  mov     rcx, rbx; string
0x180071e95  call    cs:__imp_WindowsDeleteString
0x180071e9b  nop
0x180071e9c  mov     rcx, [rbp+47h+hHash]; hHash
0x180071ea0  test    rcx, rcx
0x180071ea3  jz      short loc_180071EAC
0x180071ea5  call    cs:__imp_BCryptDestroyHash
0x180071eab  nop
0x180071eac  test    rsi, rsi
0x180071eaf  jz      short loc_180071EBA
0x180071eb1  mov     rcx, rsi; hMem
0x180071eb4  call    cs:__imp_LocalFree
0x180071eba  mov     eax, r14d
0x180071ebd  jmp     loc_180072285
0x180071ec2  xor     r9d, r9d; dwFlags
0x180071ec5  mov     r8d, r12d; cbInput
0x180071ec8  mov     rdx, [r13+0]; pbInput
0x180071ecc  mov     rcx, [rbp+47h+hHash]; hHash
0x180071ed0  call    cs:__imp_BCryptHashData
0x180071ed6  test    eax, eax
0x180071ed8  jns     short loc_180071EE1
0x180071eda  mov     edx, 374h
0x180071edf  jmp     short loc_180071E68
0x180071ee1  lea     r8, [rbp+47h+cbInput]
0x180071ee5  lea     rdx, [rbp+47h+hMem]
0x180071ee9  mov     rcx, r15; string
0x180071eec  call    ?Sha256HashString@@YAJQEAUHSTRING__@@AEAV?$unique_ptr@PEAXULocalAllocDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@PEAK@Z; Sha256HashString(HSTRING__ * const,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::LocalAllocDeleter> &,ulong *)
0x180071ef1  mov     esi, eax
0x180071ef3  test    eax, eax
0x180071ef5  jns     short loc_180071F01
0x180071ef7  mov     edx, 377h
0x180071efc  jmp     loc_180071DEB
0x180071f01  xor     r9d, r9d; dwFlags
0x180071f04  mov     r8d, [rbp+47h+cbInput]; cbInput
0x180071f08  mov     rsi, [rbp+47h+hMem]
0x180071f0c  mov     rdx, rsi; pbInput
0x180071f0f  mov     rcx, [rbp+47h+hHash]; hHash
0x180071f13  call    cs:__imp_BCryptHashData
0x180071f19  test    eax, eax
0x180071f1b  jns     short loc_180071F27
0x180071f1d  mov     edx, 379h
0x180071f22  jmp     loc_180071E68
0x180071f27  mov     dword ptr [rbp+47h+pbOutput], r14d
0x180071f2b  mov     [rbp+47h+pcbResult], r14d
0x180071f2f  mov     [rsp+100h+cbSecret], r14d; dwFlags
0x180071f34  lea     rax, [rbp+47h+pcbResult]
0x180071f38  mov     [rsp+100h+pbSecret], rax; int
0x180071f3d  mov     r9d, 4; cbOutput
0x180071f43  lea     r8, [rbp+47h+pbOutput]; pbOutput
0x180071f47  lea     rdx, pszProperty; "HashDigestLength"
0x180071f4e  mov     rcx, [rbp+47h+hHash]; hObject
0x180071f52  call    cs:__imp_BCryptGetProperty
0x180071f58  test    eax, eax
0x180071f5a  jns     short loc_180071F66
  ... truncated ...
```
