# Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::CreateProviderFromRegistration(Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *,HSTRING__ * const,HSTRING__ * const,unsigned __int64,Windows::Security::Credentials::IWebAccountProvider * *)

- ea: `0x1800295d0`
- end: `0x18002a3d0`
- name: `?CreateProviderFromRegistration@PluginRegistration@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWamProviderRegistrationInformation@Web@3456@QEAUHSTRING__@@1_KPEAPEAUIWebAccountProvider@Credentials@46@@Z`
- size: `3584`
- prototype: `static int(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *, HSTRING, HSTRING, unsigned __int64, struct Windows::Security::Credentials::IWebAccountProvider **)`
- caller_count: `7`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012ea0`
- `0x180028290`
- `0x180028adc`
- `0x180028f20`
- `0x18002928c`
- `0x18006e064`
- `0x18006e4c4`

## callees

- `0x18000bd40`
- `0x1800295d0`
- `0x1800323a0`
- `0x18003f280`
- `0x18003ffa0`
- `0x180040980`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800299dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800299dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800299c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800299c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029643`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029663`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029877`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029963`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029973`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029e59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a170`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029643`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029663`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029877`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029963`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029973`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029e59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a170`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800297d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002981a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002982a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002983a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800298d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029db2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029ec5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029fc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a09f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a0c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a1dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a206`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a2b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a2e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a37a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a38a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a399`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a3a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800297d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002981a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002982a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002983a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800298d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029db2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029ec5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029fc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a09f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a0c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a1dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a206`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a2b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a2e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a37a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a38a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a399`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a3a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002962f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002964f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180029780`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180029863`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180029884`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002962f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002964f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180029780`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180029863`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180029884`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180029a12`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180029a12`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180029769`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180029769`

## string_xrefs

- `0x1800299bc`: `Windows.Internal.Security.Credentials.WebAccountProviderInternal`
- `0x1800297b5`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`
- `0x1800297ff`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`
- `0x1800298ff`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`
- `0x18002993c`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`
- `0x180029aad`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`
- `0x180029b77`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`
- `0x180029c11`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`
- `0x180029ccb`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`
- `0x180029d97`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`
- `0x180029eaa`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`
- `0x180029f8e`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`
- `0x18002a084`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`
- `0x18002a1c1`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::CreateProviderFromRegistration(
        struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *a1,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4,
        struct Windows::Security::Credentials::IWebAccountProvider **a5)
{
  HSTRING v5; // r12
  PCWSTR v8; // rsi
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  int v14; // ecx
  HSTRING v15; // rbx
  HSTRING v16; // rdi
  int v17; // eax
  unsigned int v18; // ebx
  int v20; // eax
  unsigned int v21; // ebx
  PCWSTR v22; // rax
  int v23; // eax
  int ActivationFactory; // esi
  int v25; // eax
  __int64 (__fastcall ***v26)(_QWORD, GUID *, _QWORD *); // rcx
  int v27; // eax
  __int64 v28; // rcx
  __int64 (__fastcall ***v29)(_QWORD, GUID *, _QWORD *); // rcx
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 (__fastcall ***v33)(_QWORD, GUID *, _QWORD *); // rcx
  int v34; // eax
  struct Windows::Security::Credentials::IWebAccountProvider *v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 (__fastcall ***v38)(_QWORD, GUID *, _QWORD *); // rcx
  int v39; // eax
  __int64 v40; // rcx
  struct Windows::Security::Credentials::IWebAccountProvider *v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 (__fastcall ***v44)(_QWORD, GUID *, _QWORD *); // rcx
  int v45; // eax
  __int64 v46; // rcx
  struct Windows::Security::Credentials::IWebAccountProvider *v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 (__fastcall ***v50)(_QWORD, GUID *, _QWORD *); // rcx
  int v51; // r9d
  int v52; // eax
  __int64 v53; // rcx
  struct Windows::Security::Credentials::IWebAccountProvider *v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 (__fastcall ***v57)(_QWORD, GUID *, _QWORD *); // rcx
  int v58; // eax
  __int64 v59; // rcx
  __int64 v60; // rcx
  struct Windows::Security::Credentials::IWebAccountProvider *v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 (__fastcall ***v64)(_QWORD, GUID *, _QWORD *); // rcx
  int v65; // eax
  __int64 v66; // rcx
  __int64 v67; // rcx
  struct Windows::Security::Credentials::IWebAccountProvider *v68; // rcx
  __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 (__fastcall ***v71)(_QWORD, GUID *, _QWORD *); // rcx
  int v72; // r9d
  int v73; // eax
  __int64 v74; // rcx
  __int64 v75; // rcx
  struct Windows::Security::Credentials::IWebAccountProvider *v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 (__fastcall ***v79)(_QWORD, GUID *, _QWORD *); // rcx
  struct Windows::Security::Credentials::IWebAccountProvider *v80; // rax
  __int64 v81; // rcx
  __int64 v82; // rcx
  struct Windows::Security::Credentials::IWebAccountProvider *v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rcx
  __int64 (__fastcall ***v86)(_QWORD, GUID *, _QWORD *); // rcx
  void *UserDataCount; // [rsp+20h] [rbp-E0h]
  int UserDataCounta; // [rsp+20h] [rbp-E0h]
  __int64 v89; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v90)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-98h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v91; // [rsp+70h] [rbp-90h] BYREF
  __int64 v92; // [rsp+78h] [rbp-88h]
  __int64 v93; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v94; // [rsp+88h] [rbp-78h] BYREF
  HSTRING v95; // [rsp+90h] [rbp-70h] BYREF
  __int64 v96; // [rsp+98h] [rbp-68h] BYREF
  HSTRING v97; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING v99; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING v100; // [rsp+B8h] [rbp-48h] BYREF
  int v101[2]; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v102; // [rsp+C8h] [rbp-38h] BYREF
  int v103[2]; // [rsp+D0h] [rbp-30h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider **v104; // [rsp+D8h] [rbp-28h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+E0h] [rbp-20h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+100h] [rbp+0h] BYREF
  char *v107; // [rsp+110h] [rbp+10h]
  int v108; // [rsp+118h] [rbp+18h]
  int v109; // [rsp+11Ch] [rbp+1Ch]
  PCWSTR v110; // [rsp+120h] [rbp+20h]
  int v111; // [rsp+128h] [rbp+28h]
  int v112; // [rsp+12Ch] [rbp+2Ch]
  PCWSTR v113; // [rsp+130h] [rbp+30h]
  int v114; // [rsp+138h] [rbp+38h]
  int v115; // [rsp+13Ch] [rbp+3Ch]
  HSTRING *v116; // [rsp+140h] [rbp+40h]
  __int64 v117; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  *(_QWORD *)v101 = a4;
  v5 = a3;
  v104 = a5;
  v8 = L"null";
  if ( (unsigned int)dword_180175000 > 4 )
  {
    v100 = a4;
    if ( WindowsIsStringEmpty(a3) )
      StringRawBuffer = L"null";
    else
      StringRawBuffer = WindowsGetStringRawBuffer(v5, 0);
    if ( WindowsIsStringEmpty(a2) )
      v10 = L"null";
    else
      v10 = WindowsGetStringRawBuffer(a2, 0);
    v116 = &v100;
    v117 = 8;
    v11 = -1;
    if ( StringRawBuffer )
    {
      v12 = -1;
      do
        ++v12;
      while ( StringRawBuffer[v12] );
      v13 = 2 * v12 + 2;
    }
    else
    {
      StringRawBuffer = &word_1801330B0;
      v13 = 2;
    }
    v113 = StringRawBuffer;
    v114 = v13;
    v115 = 0;
    if ( v10 )
    {
      do
        ++v11;
      while ( v10[v11] );
      v14 = 2 * v11 + 2;
    }
    else
    {
      v10 = &word_1801330B0;
      v14 = 2;
    }
    v110 = v10;
    v111 = v14;
    v112 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 4;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_180175008;
    UserData.Size = *(unsigned __int16 *)off_180175008;
    UserData.Reserved = 2;
    v107 = &byte_1801443F7;
    v108 = 87;
    v109 = 1;
    LODWORD(string) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
  }
  v15 = 0;
  v102 = 0;
  v16 = 0;
  v100 = 0;
  if ( WindowsIsStringEmpty(a2) )
  {
    string = 0;
    v17 = (*(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *, HSTRING *))(*(_QWORD *)a1 + 48LL))(
            a1,
            &string);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\plugreg.cpp",
        (const char *)(unsigned int)v17,
        (int)UserDataCount);
      if ( string )
        WindowsDeleteString(string);
      return v18;
    }
    v20 = Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapPluginIdToAliases(
            string,
            (struct Windows::Internal::String *)&v102,
            (struct Windows::Internal::String *)&v100);
    v21 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\plugreg.cpp",
        (const char *)(unsigned int)v20,
        (int)UserDataCount);
      if ( string )
        WindowsDeleteString(string);
      if ( v100 )
        WindowsDeleteString(v100);
      if ( v102 )
        WindowsDeleteString(v102);
      return v21;
    }
    v15 = v102;
    a2 = v102;
    v16 = v100;
    v5 = v100;
    if ( (unsigned int)dword_180175000 > 5 )
    {
      if ( WindowsIsStringEmpty(v100) )
        v22 = L"null";
      else
        v22 = WindowsGetStringRawBuffer(v16, 0);
      *(_QWORD *)v103 = v22;
      if ( !WindowsIsStringEmpty(v15) )
        v8 = WindowsGetStringRawBuffer(v15, 0);
      *(_QWORD *)&EventDescriptor.Id = v8;
      UserDataCount = &EventDescriptor;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        &dword_180175000,
        &unk_180144388,
        0);
    }
    if ( string )
      WindowsDeleteString(string);
  }
  v94 = 0;
  v23 = (*(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *, HSTRING *))(*(_QWORD *)a1 + 56LL))(
          a1,
          &v94);
  ActivationFactory = v23;
  if ( v23 >= 0 )
  {
    v95 = 0;
    v25 = (*(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *, HSTRING *))(*(_QWORD *)a1 + 64LL))(
            a1,
            &v95);
    ActivationFactory = v25;
    if ( v25 >= 0 )
    {
      if ( (unsigned int)dword_180175000 > 5 )
      {
        *(_QWORD *)&EventDescriptor.Id = WindowsGetStringRawBuffer(v95, 0);
        *(_QWORD *)v103 = WindowsGetStringRawBuffer(v94, 0);
        UserDataCount = v103;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          &dword_180175000,
          byte_180144335,
          0);
      }
      v90 = 0;
      v89 = 0;
      if ( WindowsCreateStringReference(
             L"Windows.Internal.Security.Credentials.WebAccountProviderInternal",
             0x40u,
             (HSTRING_HEADER *)&EventDescriptor.Keyword,
             (HSTRING *)&EventDescriptor) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      ActivationFactory = RoGetActivationFactory(
                            *(_QWORD *)&EventDescriptor.Id,
                            &GUID_4f81bfe6_fdb4_4dc4_86b9_4af32d514b78,
                            &v90);
      if ( ActivationFactory >= 0 )
      {
        v27 = (**v90)(v90, &GUID_7f565cd8_5dff_4b5e_abdf_1bb1f8b913f3, &v89);
        ActivationFactory = v27;
        if ( v27 >= 0 )
        {
          Windows::Internal::Security::Authentication::TokenBroker::PluginManager::GetBuiltInProviderType(a2, v5);
          v92 = 0;
          UserDataCounta = (int)v5;
          v30 = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, HSTRING))(*(_QWORD *)v89 + 48LL))(
                  v89,
                  a2,
                  v94,
                  v95);
          ActivationFactory = v30;
          if ( v30 >= 0 )
          {
            v91 = 0;
            v34 = (*(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)v92 + 48LL))(
                    v92,
                    &v91);
            ActivationFactory = v34;
            if ( v34 >= 0 )
            {
              v93 = 0;
              v39 = (**(__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *))v91)(
                      v91,
                      &GUID_2b9c347e_56fb_4947_ab47_6982bb2cf28d,
                      &v93);
              ActivationFactory = v39;
              if ( v39 >= 0 )
              {
                v97 = 0;
                v45 = (*(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *, HSTRING *))(*(_QWORD *)a1 + 72LL))(
                        a1,
                        &v97);
                ActivationFactory = v45;
                if ( v45 >= 0 )
                {
                  if ( (unsigned int)dword_180175000 > 5 )
                  {
                    *(_QWORD *)v101 = WindowsGetStringRawBuffer(v97, 0);
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                      (unsigned int)&dword_180175000,
                      (unsigned int)&dword_1801442F4,
                      0,
                      v51,
                      (__int64)v101);
                  }
                  v52 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v93 + 56LL))(v93, v97);
                  ActivationFactory = v52;
                  if ( v52 >= 0 )
                  {
                    v96 = 0;
                    v58 = (**(__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *))v91)(
                            v91,
                            &GUID_3b043d7e_726f_41e2_8933_f968f503b854,
                            &v96);
                    ActivationFactory = v58;
                    if ( v58 >= 0 )
                    {
                      v99 = 0;
                      v65 = (*(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *, HSTRING *))(*(_QWORD *)a1 + 96LL))(
                              a1,
                              &v99);
                      ActivationFactory = v65;
                      if ( v65 >= 0 )
                      {
                        if ( (unsigned int)dword_180175000 > 5 )
                        {
                          *(_QWORD *)v101 = WindowsGetStringRawBuffer(v99, 0);
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                            (unsigned int)&dword_180175000,
                            (unsigned int)byte_1801442B1,
                            0,
                            v72,
                            (__int64)v101);
                        }
                        v73 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v96 + 96LL))(v96, v99);
                        ActivationFactory = v73;
                        if ( v73 >= 0 )
                        {
                          v80 = v91;
                          v91 = 0;
                          *v104 = v80;
                          if ( v99 )
                            WindowsDeleteString(v99);
                          v81 = v96;
                          if ( v96 )
                          {
                            v96 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
                          }
                          if ( v97 )
                            WindowsDeleteString(v97);
                          v82 = v93;
                          if ( v93 )
                          {
                            v93 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
                          }
                          v83 = v91;
                          if ( v91 )
                          {
                            v91 = 0;
                            (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)v83 + 16LL))(v83);
                          }
                          v84 = v92;
                          if ( v92 )
                          {
                            v92 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
                          }
                          v85 = v89;
                          if ( v89 )
                          {
                            v89 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
                          }
                          v86 = v90;
                          if ( v90 )
                          {
                            v90 = 0;
                            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v86)[2])(v86);
                          }
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0xBA,
                            (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\plugreg.cpp",
                            (const char *)(unsigned int)v73,
                            UserDataCounta);
                          if ( v99 )
                            WindowsDeleteString(v99);
                          v74 = v96;
                          if ( v96 )
                          {
                            v96 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
                          }
                          if ( v97 )
                            WindowsDeleteString(v97);
                          v75 = v93;
                          if ( v93 )
                          {
                            v93 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
                          }
                          v76 = v91;
                          if ( v91 )
                          {
                            v91 = 0;
                            (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)v76 + 16LL))(v76);
                          }
                          v77 = v92;
                          if ( v92 )
                          {
                            v92 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
                          }
                          v78 = v89;
                          if ( v89 )
                          {
                            v89 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
                          }
                          v79 = v90;
                          if ( v90 )
                          {
                            v90 = 0;
                            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v79)[2])(v79);
                          }
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0xB2,
                          (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\plugreg.cpp",
                          (const char *)(unsigned int)v65,
                          UserDataCounta);
                        if ( v99 )
                          WindowsDeleteString(v99);
                        v66 = v96;
                        if ( v96 )
                        {
                          v96 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
                        }
                        if ( v97 )
                          WindowsDeleteString(v97);
                        v67 = v93;
                        if ( v93 )
                        {
                          v93 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
                        }
                        v68 = v91;
                        if ( v91 )
                        {
                          v91 = 0;
                          (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)v68 + 16LL))(v68);
                        }
                        v69 = v92;
                        if ( v92 )
                        {
                          v92 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
                        }
                        v70 = v89;
                        if ( v89 )
                        {
                          v89 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
                        }
                        v71 = v90;
                        if ( v90 )
                        {
                          v90 = 0;
                          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v71)[2])(v71);
                        }
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0xAF,
                        (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\plugreg.cpp",
                        (const char *)(unsigned int)v58,
                        UserDataCounta);
                      v59 = v96;
                      if ( v96 )
                      {
                        v96 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
                      }
                      if ( v97 )
                        WindowsDeleteString(v97);
                      v60 = v93;
                      if ( v93 )
                      {
                        v93 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
                      }
                      v61 = v91;
                      if ( v91 )
                      {
                        v91 = 0;
                        (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)v61 + 16LL))(v61);
                      }
                      v62 = v92;
                      if ( v92 )
                      {
                        v92 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
                      }
                      v63 = v89;
                      if ( v89 )
                      {
                        v89 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
                      }
                      v64 = v90;
                      if ( v90 )
                      {
                        v90 = 0;
                        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v64)[2])(v64);
                      }
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xAC,
                      (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\plugreg.cpp",
                      (const char *)(unsigned int)v52,
                      UserDataCounta);
                    if ( v97 )
                      WindowsDeleteString(v97);
                    v53 = v93;
                    if ( v93 )
                    {
                      v93 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
                    }
                    v54 = v91;
                    if ( v91 )
                    {
                      v91 = 0;
                      (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)v54 + 16LL))(v54);
                    }
                    v55 = v92;
                    if ( v92 )
                    {
                      v92 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
                    }
                    v56 = v89;
                    if ( v89 )
                    {
                      v89 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
                    }
                    v57 = v90;
                    if ( v90 )
                    {
                      v90 = 0;
                      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v57)[2])(v57);
                    }
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xA3,
                    (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\plugreg.cpp",
                    (const char *)(unsigned int)v45,
                    (int)v5);
                  if ( v97 )
                    WindowsDeleteString(v97);
                  v46 = v93;
                  if ( v93 )
                  {
                    v93 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
                  }
                  v47 = v91;
                  if ( v91 )
                  {
                    v91 = 0;
                    (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)v47 + 16LL))(v47);
                  }
                  v48 = v92;
                  if ( v92 )
                  {
                    v92 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
                  }
                  v49 = v89;
                  if ( v89 )
                  {
                    v89 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
                  }
                  v50 = v90;
                  if ( v90 )
                  {
                    v90 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v50)[2])(v50);
                  }
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xA0,
                  (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\plugreg.cpp",
                  (const char *)(unsigned int)v39,
                  (int)v5);
                v40 = v93;
                if ( v93 )
                {
                  v93 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
                }
                v41 = v91;
                if ( v91 )
                {
                  v91 = 0;
                  (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)v41 + 16LL))(v41);
                }
                v42 = v92;
                if ( v92 )
                {
                  v92 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
                }
                v43 = v89;
                if ( v89 )
                {
                  v89 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
                }
                v44 = v90;
                if ( v90 )
                {
                  v90 = 0;
                  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v44)[2])(v44);
                }
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x9D,
                (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\plugreg.cpp",
                (const char *)(unsigned int)v34,
                (int)v5);
              v35 = v91;
              if ( v91 )
              {
                v91 = 0;
                (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)v35 + 16LL))(v35);
              }
              v36 = v92;
              if ( v92 )
              {
                v92 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              }
              v37 = v89;
              if ( v89 )
              {
                v89 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
              }
              v38 = v90;
              if ( v90 )
              {
                v90 = 0;
                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v38)[2])(v38);
              }
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x99,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\plugreg.cpp",
              (const char *)(unsigned int)v30,
              (int)v5);
            v31 = v92;
            if ( v92 )
            {
              v92 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
            }
            v32 = v89;
            if ( v89 )
            {
              v89 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
            }
            v33 = v90;
            if ( v90 )
            {
              v90 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v33)[2])(v33);
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x85,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\plugreg.cpp",
            (const char *)(unsigned int)v27,
            (int)UserDataCount);
          v28 = v89;
          if ( v89 )
          {
            v89 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          }
          v29 = v90;
          if ( v90 )
          {
            v90 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v29)[2])(v29);
          }
        }
      }
      else
      {
        v26 = v90;
        if ( v90 )
        {
          v90 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v26)[2])(v26);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\plugreg.cpp",
        (const char *)(unsigned int)v25,
        (int)UserDataCount);
    }
    if ( v95 )
      WindowsDeleteString(v95);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\plugreg.cpp",
      (const char *)(unsigned int)v23,
      (int)UserDataCount);
  }
  if ( v94 )
    WindowsDeleteString(v94);
  if ( v16 )
    WindowsDeleteString(v16);
  if ( v15 )
    WindowsDeleteString(v15);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800295d0  push    rbp
0x1800295d2  push    rbx
0x1800295d3  push    rsi
0x1800295d4  push    rdi
0x1800295d5  push    r12
0x1800295d7  push    r13
0x1800295d9  push    r14
0x1800295db  push    r15
0x1800295dd  lea     rbp, [rsp-68h]
0x1800295e2  sub     rsp, 168h
0x1800295e9  mov     rax, cs:__security_cookie
0x1800295f0  xor     rax, rsp
0x1800295f3  mov     [rbp+0A0h+var_50], rax
0x1800295f7  mov     qword ptr [rbp+0A0h+var_E0], r9
0x1800295fb  mov     r12, r8
0x1800295fe  mov     r14, rdx
0x180029601  mov     r15, rcx
0x180029604  mov     rax, [rbp+0A0h+arg_20]
0x18002960b  mov     [rbp+0A0h+var_C8], rax
0x18002960f  mov     eax, cs:dword_180175000
0x180029615  lea     rsi, aNull; "null"
0x18002961c  xor     r13d, r13d
0x18002961f  cmp     eax, 4
0x180029622  jbe     loc_18002976F
0x180029628  mov     [rbp+0A0h+var_E8], r9
0x18002962c  mov     rcx, r8; string
0x18002962f  call    cs:__imp_WindowsIsStringEmpty
0x180029635  test    eax, eax
0x180029637  jz      short loc_18002963E
0x180029639  mov     rbx, rsi
0x18002963c  jmp     short loc_18002964C
0x18002963e  xor     edx, edx; length
0x180029640  mov     rcx, r12; string
0x180029643  call    cs:__imp_WindowsGetStringRawBuffer
0x180029649  mov     rbx, rax
0x18002964c  mov     rcx, r14; string
0x18002964f  call    cs:__imp_WindowsIsStringEmpty
0x180029655  test    eax, eax
0x180029657  jz      short loc_18002965E
0x180029659  mov     rdx, rsi
0x18002965c  jmp     short loc_18002966C
0x18002965e  xor     edx, edx; length
0x180029660  mov     rcx, r14; string
0x180029663  call    cs:__imp_WindowsGetStringRawBuffer
0x180029669  mov     rdx, rax
0x18002966c  lea     rax, [rbp+0A0h+var_E8]
0x180029670  mov     [rbp+0A0h+var_60], rax
0x180029674  mov     [rbp+0A0h+var_58], 8
0x18002967c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180029683  test    rbx, rbx
0x180029686  jz      short loc_1800296A4
0x180029688  mov     rax, rcx
0x18002968b  nop     dword ptr [rax+rax+00h]
0x180029690  lea     rax, [rax+1]
0x180029694  cmp     [rbx+rax*2], r13w
0x180029699  jnz     short loc_180029690
0x18002969b  lea     eax, ds:2[rax*2]
0x1800296a2  jmp     short loc_1800296B0
0x1800296a4  lea     rbx, word_1801330B0
0x1800296ab  mov     eax, 2
0x1800296b0  mov     [rbp+0A0h+var_70], rbx
0x1800296b4  mov     [rbp+0A0h+var_68], eax
0x1800296b7  mov     [rbp+0A0h+var_64], r13d
0x1800296bb  test    rdx, rdx
0x1800296be  jz      short loc_1800296D4
0x1800296c0  lea     rcx, [rcx+1]
0x1800296c4  cmp     [rdx+rcx*2], r13w
0x1800296c9  jnz     short loc_1800296C0
0x1800296cb  lea     ecx, ds:2[rcx*2]
0x1800296d2  jmp     short loc_1800296E0
0x1800296d4  lea     rdx, word_1801330B0
0x1800296db  mov     ecx, 2
0x1800296e0  mov     [rbp+0A0h+var_80], rdx
0x1800296e4  mov     [rbp+0A0h+var_78], ecx
0x1800296e7  mov     [rbp+0A0h+var_74], r13d
0x1800296eb  mov     dword ptr [rbp+0A0h+EventDescriptor.Id], 0B000000h
0x1800296f2  movzx   eax, cs:word_1801443ED
0x1800296f9  mov     dword ptr [rbp+0A0h+EventDescriptor.Level], eax
0x1800296fc  mov     [rbp+0A0h+EventDescriptor.Keyword], r13
0x180029700  mov     rax, cs:off_180175008
0x180029707  mov     [rbp+0A0h+var_A0.Ptr], rax
0x18002970b  movzx   eax, word ptr [rax]
0x18002970e  mov     [rbp+0A0h+var_A0.Size], eax
0x180029711  mov     dword ptr [rbp+0A0h+var_A0.0Ch], 2
0x180029718  lea     rax, byte_1801443F7
0x18002971f  mov     [rbp+0A0h+var_90], rax
0x180029723  mov     [rbp+0A0h+var_88], 57h ; 'W'
0x18002972a  mov     [rbp+0A0h+var_84], 1
0x180029731  lea     rax, _TraceLoggingMetadataEnd
0x180029738  lea     rcx, _TraceLoggingMetadata
0x18002973f  sub     eax, ecx
0x180029741  mov     dword ptr [rbp+0A0h+string], eax
0x180029744  mov     eax, dword ptr [rbp+0A0h+string]
0x180029747  lea     rax, [rbp+0A0h+var_A0]
0x18002974b  mov     [rsp+1A0h+UserData], rax; UserData
0x180029750  mov     [rsp+1A0h+UserDataCount], 5; int
0x180029758  xor     r9d, r9d; RelatedActivityId
0x18002975b  xor     r8d, r8d; ActivityId
0x18002975e  lea     rdx, [rbp+0A0h+EventDescriptor]; EventDescriptor
0x180029762  mov     rcx, cs:RegHandle; RegHandle
0x180029769  call    cs:__imp_EventWriteTransfer
0x18002976f  mov     rbx, r13
0x180029772  mov     [rbp+0A0h+var_D8], rbx
0x180029776  mov     rdi, r13
0x180029779  mov     [rbp+0A0h+var_E8], r13
0x18002977d  mov     rcx, r14; string
0x180029780  call    cs:__imp_WindowsIsStringEmpty
0x180029786  test    eax, eax
0x180029788  jz      loc_1800298D8
0x18002978e  mov     [rbp+0A0h+string], r13
0x180029792  mov     rax, [r15]
0x180029795  lea     rdx, [rbp+0A0h+string]
0x180029799  mov     rcx, r15
0x18002979c  mov     rax, [rax+30h]
0x1800297a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297a5  mov     ebx, eax
0x1800297a7  test    eax, eax
0x1800297a9  jns     short loc_1800297DE
0x1800297ab  mov     rcx, [rbp+0A8h]; this
0x1800297b2  mov     r9d, eax; char *
0x1800297b5  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\tokenbroker\\plu"...
0x1800297bc  mov     edx, 59h ; 'Y'; void *
0x1800297c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800297c6  nop
0x1800297c7  mov     rcx, [rbp+0A0h+string]; string
0x1800297cb  test    rcx, rcx
0x1800297ce  jz      short loc_1800297D7
0x1800297d0  call    cs:__imp_WindowsDeleteString
0x1800297d6  nop
0x1800297d7  mov     eax, ebx
0x1800297d9  jmp     loc_18002A3B0
0x1800297de  lea     r8, [rbp+0A0h+var_E8]; struct Windows::Internal::String *
0x1800297e2  lea     rdx, [rbp+0A0h+var_D8]; struct Windows::Internal::String *
0x1800297e6  mov     rcx, [rbp+0A0h+string]; string2
0x1800297ea  call    ?MapPluginIdToAliases@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUHSTRING__@@AEAVString@56@1@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapPluginIdToAliases(HSTRING__ *,Windows::Internal::String &,Windows::Internal::String &)
0x1800297ef  mov     ebx, eax
0x1800297f1  test    eax, eax
0x1800297f3  jns     short loc_180029847
0x1800297f5  mov     rcx, [rbp+0A8h]; this
0x1800297fc  mov     r9d, eax; char *
0x1800297ff  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\tokenbroker\\plu"...
0x180029806  mov     edx, 5Eh ; '^'; void *
0x18002980b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029810  nop
0x180029811  mov     rcx, [rbp+0A0h+string]; string
0x180029815  test    rcx, rcx
0x180029818  jz      short loc_180029821
0x18002981a  call    cs:__imp_WindowsDeleteString
0x180029820  nop
0x180029821  mov     rcx, [rbp+0A0h+var_E8]; string
0x180029825  test    rcx, rcx
0x180029828  jz      short loc_180029831
0x18002982a  call    cs:__imp_WindowsDeleteString
0x180029830  nop
0x180029831  mov     rcx, [rbp+0A0h+var_D8]; string
0x180029835  test    rcx, rcx
0x180029838  jz      short loc_180029840
0x18002983a  call    cs:__imp_WindowsDeleteString
0x180029840  mov     eax, ebx
0x180029842  jmp     loc_18002A3B0
0x180029847  mov     rbx, [rbp+0A0h+var_D8]
0x18002984b  mov     r14, rbx
0x18002984e  mov     rdi, [rbp+0A0h+var_E8]
0x180029852  mov     r12, rdi
0x180029855  mov     eax, cs:dword_180175000
0x18002985b  cmp     eax, 5
0x18002985e  jbe     short loc_1800298C9
0x180029860  mov     rcx, rdi; string
0x180029863  call    cs:__imp_WindowsIsStringEmpty
0x180029869  test    eax, eax
0x18002986b  jz      short loc_180029872
0x18002986d  mov     rax, rsi
0x180029870  jmp     short loc_18002987D
0x180029872  xor     edx, edx; length
0x180029874  mov     rcx, rdi; string
0x180029877  call    cs:__imp_WindowsGetStringRawBuffer
0x18002987d  mov     qword ptr [rbp+0A0h+var_D0], rax
0x180029881  mov     rcx, rbx; string
0x180029884  call    cs:__imp_WindowsIsStringEmpty
0x18002988a  test    eax, eax
0x18002988c  jnz     short loc_18002989C
0x18002988e  xor     edx, edx; length
0x180029890  mov     rcx, rbx; string
0x180029893  call    cs:__imp_WindowsGetStringRawBuffer
0x180029899  mov     rsi, rax
0x18002989c  mov     qword ptr [rbp+0A0h+EventDescriptor.Id], rsi
0x1800298a0  lea     rax, [rbp+0A0h+var_D0]
0x1800298a4  mov     [rsp+1A0h+UserData], rax
0x1800298a9  lea     rax, [rbp+0A0h+EventDescriptor]
0x1800298ad  mov     qword ptr [rsp+1A0h+UserDataCount], rax; int
0x1800298b2  xor     r8d, r8d
0x1800298b5  lea     rdx, unk_180144388
0x1800298bc  lea     rcx, dword_180175000
0x1800298c3  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800298c8  nop
0x1800298c9  mov     rcx, [rbp+0A0h+string]; string
0x1800298cd  test    rcx, rcx
0x1800298d0  jz      short loc_1800298D8
0x1800298d2  call    cs:__imp_WindowsDeleteString
0x1800298d8  mov     [rbp+0A0h+var_118], r13
0x1800298dc  mov     rax, [r15]
0x1800298df  lea     rdx, [rbp+0A0h+var_118]
0x1800298e3  mov     rcx, r15
0x1800298e6  mov     rax, [rax+38h]
0x1800298ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298ef  mov     esi, eax
0x1800298f1  test    eax, eax
0x1800298f3  jns     short loc_180029915
0x1800298f5  mov     rcx, [rbp+0A8h]; this
0x1800298fc  mov     r9d, eax; char *
0x1800298ff  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\tokenbroker\\plu"...
0x180029906  mov     edx, 74h ; 't'; void *
0x18002990b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029910  jmp     loc_18002A381
0x180029915  mov     [rbp+0A0h+var_110], r13
0x180029919  mov     rax, [r15]
0x18002991c  lea     rdx, [rbp+0A0h+var_110]
0x180029920  mov     rcx, r15
0x180029923  mov     rax, [rax+40h]
0x180029927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002992c  mov     esi, eax
0x18002992e  test    eax, eax
0x180029930  jns     short loc_180029952
0x180029932  mov     rcx, [rbp+0A8h]; this
0x180029939  mov     r9d, eax; char *
0x18002993c  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\tokenbroker\\plu"...
0x180029943  mov     edx, 77h ; 'w'; void *
0x180029948  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002994d  jmp     loc_18002A371
0x180029952  mov     eax, cs:dword_180175000
0x180029958  cmp     eax, 5
0x18002995b  jbe     short loc_1800299A5
0x18002995d  xor     edx, edx; length
0x18002995f  mov     rcx, [rbp+0A0h+var_110]; string
0x180029963  call    cs:__imp_WindowsGetStringRawBuffer
0x180029969  mov     qword ptr [rbp+0A0h+EventDescriptor.Id], rax
0x18002996d  xor     edx, edx; length
0x18002996f  mov     rcx, [rbp+0A0h+var_118]; string
0x180029973  call    cs:__imp_WindowsGetStringRawBuffer
0x180029979  mov     qword ptr [rbp+0A0h+var_D0], rax
0x18002997d  lea     rax, [rbp+0A0h+EventDescriptor]
0x180029981  mov     [rsp+1A0h+UserData], rax
0x180029986  lea     rax, [rbp+0A0h+var_D0]
0x18002998a  mov     qword ptr [rsp+1A0h+UserDataCount], rax; int
0x18002998f  xor     r8d, r8d
0x180029992  lea     rdx, byte_180144335
0x180029999  lea     rcx, dword_180175000
0x1800299a0  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800299a5  mov     [rsp+1A0h+var_138], r13
0x1800299aa  mov     [rsp+1A0h+var_140], r13
0x1800299af  lea     r9, [rbp+0A0h+EventDescriptor]; string
0x1800299b3  lea     r8, [rbp+0A0h+EventDescriptor.Keyword]; hstringHeader
0x1800299b7  mov     edx, 40h ; '@'; length
0x1800299bc  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Credentials_WebAccountProviderInternal@@3QBGB; "Windows.Internal.Security.Credentials.W"...
0x1800299c3  call    cs:__imp_WindowsCreateStringReference
0x1800299c9  test    eax, eax
0x1800299cb  jns     short loc_1800299E3
0x1800299cd  xor     r9d, r9d; lpArguments
0x1800299d0  xor     r8d, r8d; nNumberOfArguments
0x1800299d3  mov     edx, 1; dwExceptionFlags
0x1800299d8  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800299dd  call    cs:__imp_RaiseException
0x1800299e3  mov     rsi, qword ptr [rbp+0A0h+EventDescriptor.Id]
0x1800299e7  mov     rcx, [rsp+1A0h+var_138]
0x1800299ec  test    rcx, rcx
0x1800299ef  jz      short loc_180029A03
0x1800299f1  mov     [rsp+1A0h+var_138], r13
0x1800299f6  mov     rax, [rcx]
0x1800299f9  mov     rax, [rax+10h]
0x1800299fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a02  nop
0x180029a03  lea     r8, [rsp+1A0h+var_138]
0x180029a08  lea     rdx, _GUID_4f81bfe6_fdb4_4dc4_86b9_4af32d514b78
0x180029a0f  mov     rcx, rsi
0x180029a12  call    cs:__imp_RoGetActivationFactory
0x180029a18  mov     esi, eax
0x180029a1a  test    eax, eax
0x180029a1c  jns     short loc_180029A5B
0x180029a1e  mov     rcx, [rsp+1A0h+var_140]
0x180029a23  test    rcx, rcx
0x180029a26  jz      short loc_180029A3A
0x180029a28  mov     [rsp+1A0h+var_140], r13
0x180029a2d  mov     rdx, [rcx]
0x180029a30  mov     rax, [rdx+10h]
0x180029a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a39  nop
0x180029a3a  mov     rcx, [rsp+1A0h+var_138]
0x180029a3f  test    rcx, rcx
0x180029a42  jz      short loc_180029A56
0x180029a44  mov     [rsp+1A0h+var_138], r13
0x180029a49  mov     rax, [rcx]
0x180029a4c  mov     rax, [rax+10h]
0x180029a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a55  nop
0x180029a56  jmp     loc_18002A371
0x180029a5b  mov     rsi, [rsp+1A0h+var_138]
0x180029a60  mov     rax, [rsi]
0x180029a63  mov     r13, [rax]
0x180029a66  mov     rcx, [rsp+1A0h+var_140]
0x180029a6b  test    rcx, rcx
  ... truncated ...
```
