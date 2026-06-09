# SubscriptionConfigWriter::Validate(void)

- ea: `0x180017b8c`
- end: `0x1800189e2`
- name: `?Validate@SubscriptionConfigWriter@@AEAA?AW4_EC_SUBSCRIPTION_TYPE@@XZ`
- size: `3670`
- prototype: `_BOOL8 __fastcall(SubscriptionConfigWriter *this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800165c0`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x1800062d4`
- `0x1800128c0`
- `0x1800161e4`
- `0x18001632c`
- `0x180016358`
- `0x180017b8c`
- `0x18001de6c`
- `0x18001e0cc`
- `0x18001e18c`
- `0x18001e20c`
- `0x18001e660`
- `0x18001e734`
- `0x18001f9cc`
- `0x18001fe50`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180017c39`
- `msvcrt!_wcsicmp` at `0x180017c39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ded`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ded`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180017ddf`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180017ddf`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017cfe`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017cfe`

## string_xrefs

- `0x180017c32`: `http://schemas.microsoft.com/wbem/wsman/1/windows/EventLog`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall SubscriptionConfigWriter::Validate(SubscriptionConfigWriter *this)
{
  SubscriptionWriteData *v2; // rbx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v3; // edx
  const wchar_t *v4; // rcx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v5; // edx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v6; // r9d
  __int64 v7; // rdx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v8; // edx
  unsigned int v9; // edx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v10; // edx
  __int64 v11; // rdx
  const WCHAR *p_pExceptionObject; // rcx
  DWORD LastError; // ebx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v14; // edx
  enum _EC_SUBSCRIPTION_DELIVERY_MODE DeliveryMode; // eax
  enum _EC_SUBSCRIPTION_PROPERTY_ID v16; // edx
  unsigned int v17; // r9d
  enum _EC_SUBSCRIPTION_PROPERTY_ID v18; // edx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v19; // edx
  bool v20; // di
  enum _EC_SUBSCRIPTION_PROPERTY_ID v21; // edx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v22; // edx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v23; // edx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v24; // edx
  __int64 v25; // rdx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v26; // edx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v27; // edx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v28; // edx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v29; // edx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v30; // edx
  __int64 v31; // rdx
  void **v33; // [rsp+20h] [rbp-69h] BYREF
  char v34; // [rsp+28h] [rbp-61h]
  const char *v35; // [rsp+30h] [rbp-59h]
  __int64 v36; // [rsp+38h] [rbp-51h]
  __int64 v37; // [rsp+40h] [rbp-49h]
  int v38; // [rsp+48h] [rbp-41h]
  int v39; // [rsp+4Ch] [rbp-3Dh]
  int v40; // [rsp+50h] [rbp-39h]
  FILETIME FileTime2; // [rsp+58h] [rbp-31h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-29h] BYREF
  char v43; // [rsp+68h] [rbp-21h]
  const char *v44; // [rsp+70h] [rbp-19h]
  unsigned __int64 v45; // [rsp+78h] [rbp-11h]
  __int64 v46; // [rsp+80h] [rbp-9h]
  int v47; // [rsp+88h] [rbp-1h]
  int v48; // [rsp+8Ch] [rbp+3h]
  int v49; // [rsp+90h] [rbp+7h]
  wchar_t *String1[2]; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v51; // [rsp+A8h] [rbp+1Fh]
  unsigned __int64 v52; // [rsp+B0h] [rbp+27h]

  v52 = 7;
  v51 = 0;
  LOWORD(String1[0]) = 0;
  v2 = (SubscriptionConfigWriter *)((char *)this + 24);
  if ( !SubscriptionWriteData::IsDirty((SubscriptionConfigWriter *)((char *)this + 24), EcSubscriptionURI)
    || SubscriptionWriteData::IsCleared(v2, v3) )
  {
    if ( SubscriptionWriteData::IsDirty(v2, EcSubscriptionURI) )
      goto LABEL_10;
    RegReadStringValue(*((_QWORD *)this + 2), L"URI", String1);
  }
  else
  {
    SubscriptionReadData::GetURI(v2, String1);
  }
  if ( !v51 )
    goto LABEL_10;
  v4 = (const wchar_t *)String1;
  if ( v52 >= 8 )
    v4 = String1[0];
  if ( !_wcsicmp(v4, L"http://schemas.microsoft.com/wbem/wsman/1/windows/EventLog") )
  {
LABEL_10:
    v45 = 7;
    v44 = 0;
    LOWORD(pExceptionObject) = 0;
    if ( !SubscriptionWriteData::IsDirty(v2, EcSubscriptionQuery) || SubscriptionWriteData::IsCleared(v2, v5) )
    {
      if ( SubscriptionWriteData::IsDirty(v2, v6) )
        goto LABEL_155;
      RegReadStringValue(*((_QWORD *)this + 2), L"Query", &pExceptionObject);
    }
    else
    {
      SubscriptionReadData::GetQuery(v2, &pExceptionObject);
    }
    if ( v44 )
    {
      LOBYTE(v7) = 1;
      std::wstring::_Tidy(&pExceptionObject, v7, 0);
      goto LABEL_17;
    }
LABEL_155:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 15085);
    }
    v34 = 0;
    v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
    v36 = 0;
    v37 = 0;
    v38 = 15085;
    v39 = -1;
    v40 = 1003;
    v33 = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&v33;
  }
LABEL_17:
  if ( SubscriptionWriteData::IsDirty(v2, EcSubscriptionExpires) && !SubscriptionWriteData::IsCleared(v2, v8) )
  {
    FileTime2 = 0;
    ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)v2, v9, &FileTime2);
    if ( CompareFileTime(&FileTime1, &FileTime2) == -1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 87);
      }
      v43 = 0;
      v44 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v45 = 0;
      v46 = 0;
      v47 = 87;
      v48 = -1;
      v49 = 1016;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
  if ( SubscriptionWriteData::IsDirty(v2, EcSubscriptionLocale) && !SubscriptionWriteData::IsCleared(v2, v10) )
  {
    v45 = 7;
    v44 = 0;
    LOWORD(pExceptionObject) = 0;
    SubscriptionReadData::GetLocale(v2, &pExceptionObject);
    if ( v44 )
    {
      p_pExceptionObject = (const WCHAR *)&pExceptionObject;
      if ( v45 >= 8 )
        p_pExceptionObject = (const WCHAR *)pExceptionObject;
      if ( !LocaleNameToLCID(p_pExceptionObject, 0) )
      {
        LastError = GetLastError();
        if ( !LastError )
          LastError = 1287;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, LastError);
        }
        v34 = 0;
        v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
        v36 = 0;
        v37 = 0;
        v38 = LastError;
        v39 = -1;
        v40 = 1030;
        v33 = &wmi::GenericException::`vftable';
        throw (wmi::GenericException *)&v33;
      }
    }
    LOBYTE(v11) = 1;
    std::wstring::_Tidy(&pExceptionObject, v11, 0);
  }
  if ( SubscriptionWriteData::IsDirty(v2, EcSubscriptionDeliveryMode) && !SubscriptionWriteData::IsCleared(v2, v14) )
  {
    DeliveryMode = SubscriptionReadData::GetDeliveryMode(v2);
    if ( !EnumValueToName((struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueDeliveryMode, DeliveryMode) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 13);
      }
      v34 = 0;
      v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v36 = 0;
      v37 = 0;
      v38 = 13;
      v39 = -1;
      v40 = 1037;
      v33 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v33;
    }
  }
  if ( SubscriptionWriteData::IsDirty(v2, EcSubscriptionContentFormat) && !SubscriptionWriteData::IsCleared(v2, v16) )
  {
    FileTime2.dwLowDateTime = 2;
    ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)v2, v17, (unsigned int *)&FileTime2);
    if ( !EnumValueToName((struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueContentFormat, FileTime2.dwLowDateTime) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 13);
      }
      v34 = 0;
      v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v36 = 0;
      v37 = 0;
      v38 = 13;
      v39 = -1;
      v40 = 1042;
      v33 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v33;
    }
  }
  if ( SubscriptionWriteData::IsDirty(v2, EcSubscriptionConfigurationMode) && !SubscriptionWriteData::IsCleared(v2, v18) )
  {
    FileTime2.dwLowDateTime = 1;
    ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)v2, 8u, (unsigned int *)&FileTime2);
    if ( !EnumValueToName((struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueConfigurationMode, FileTime2.dwLowDateTime) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 13);
      }
      v34 = 0;
      v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v36 = 0;
      v37 = 0;
      v38 = 13;
      v39 = -1;
      v40 = 1047;
      v33 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v33;
    }
  }
  if ( SubscriptionWriteData::IsDirty(v2, EcSubscriptionCredentialsType) && !SubscriptionWriteData::IsCleared(v2, v19) )
  {
    FileTime2.dwLowDateTime = 0;
    ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)v2, 0x15u, (unsigned int *)&FileTime2);
    if ( !EnumValueToName((struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueCredentialsType, FileTime2.dwLowDateTime) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 13);
      }
      v34 = 0;
      v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v36 = 0;
      v37 = 0;
      v38 = 13;
      v39 = -1;
      v40 = 1052;
      v33 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v33;
    }
  }
  v20 = 1;
  if ( !SubscriptionWriteData::IsDirty(v2, EcSubscriptionType) || SubscriptionWriteData::IsCleared(v2, v21) )
  {
    FileTime2.dwLowDateTime = 0;
    if ( ConfigBase::GetRegEnumValue(
           this,
           L"SubscriptionType",
           (struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueSubscriptionType,
           (unsigned int *)&FileTime2) )
    {
      v20 = FileTime2.dwLowDateTime != 0;
    }
  }
  else
  {
    FileTime2.dwLowDateTime = 1;
    ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)v2, 0x1Bu, (unsigned int *)&FileTime2);
    if ( !EnumValueToName((struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueSubscriptionType, FileTime2.dwLowDateTime) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 13);
      }
      v34 = 0;
      v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v36 = 0;
      v37 = 0;
      v38 = 13;
      v39 = -1;
      v40 = 1061;
      v33 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v33;
    }
    FileTime2.dwLowDateTime = 1;
    ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)v2, 0x1Bu, (unsigned int *)&FileTime2);
    v20 = FileTime2.dwLowDateTime != 0;
  }
  v45 = 7;
  v44 = 0;
  LOWORD(pExceptionObject) = 0;
  if ( v20 )
  {
    if ( SubscriptionWriteData::IsDirty(v2, EcSubscriptionAllowedIssuerCAs)
      && !SubscriptionWriteData::IsCleared(v2, v22) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 13);
      }
      v34 = 0;
      v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v36 = 0;
      v37 = 0;
      v38 = 13;
      v39 = -1;
      v40 = 1083;
      v33 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v33;
    }
    if ( SubscriptionWriteData::IsDirty(v2, EcSubscriptionAllowedSubjects) && !SubscriptionWriteData::IsCleared(v2, v23) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 13);
      }
      v34 = 0;
      v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v36 = 0;
      v37 = 0;
      v38 = 13;
      v39 = -1;
      v40 = 1089;
      v33 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v33;
    }
    if ( SubscriptionWriteData::IsDirty(v2, EcSubscriptionDeniedSubjects) && !SubscriptionWriteData::IsCleared(v2, v24) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 13);
      }
      v34 = 0;
      v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v36 = 0;
      v37 = 0;
      v38 = 13;
      v39 = -1;
      v40 = 1095;
      v33 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v33;
    }
    if ( SubscriptionWriteData::IsDirty(v2, EcSubscriptionAllowedSourceDomainComputers)
      && !SubscriptionWriteData::IsCleared(v2, (enum _EC_SUBSCRIPTION_PROPERTY_ID)v25) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 13);
      }
      v34 = 0;
      v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v36 = 0;
      v37 = 0;
      v38 = 13;
      v39 = -1;
      v40 = 1101;
      v33 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v33;
    }
  }
  else
  {
    if ( SubscriptionWriteData::IsDirty(v2, EcSubscriptionEventSourceUserName)
      && !SubscriptionWriteData::IsCleared(v2, v26) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 13);
      }
      v34 = 0;
      v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v36 = 0;
      v37 = 0;
      v38 = 13;
      v39 = -1;
      v40 = 1109;
      v33 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v33;
    }
    if ( SubscriptionWriteData::IsDirty(v2, EcSubscriptionEventSourcePassword)
      && !SubscriptionWriteData::IsCleared(v2, v27) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 13);
      }
      v34 = 0;
      v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v36 = 0;
      v37 = 0;
      v38 = 13;
      v39 = -1;
      v40 = 1115;
      v33 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v33;
    }
    if ( SubscriptionWriteData::IsDirty(v2, EcSubscriptionDeliveryMode)
      && !SubscriptionWriteData::IsCleared(v2, v28)
      && SubscriptionReadData::GetDeliveryMode(v2) != EcDeliveryModePush )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 13);
      }
      v34 = 0;
      v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v36 = 0;
      v37 = 0;
      v38 = 13;
      v39 = -1;
      v40 = 1122;
      v33 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v33;
    }
    if ( SubscriptionWriteData::IsDirty(v2, EcSubscriptionCredentialsType) && !SubscriptionWriteData::IsCleared(v2, v29) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 13);
      }
      v34 = 0;
      v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v36 = 0;
      v37 = 0;
      v38 = 13;
      v39 = -1;
      v40 = 1128;
      v33 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v33;
    }
    if ( SubscriptionWriteData::IsDirty(v2, EcSubscriptionCommonUserName) && !SubscriptionWriteData::IsCleared(v2, v30) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 13);
      }
      v34 = 0;
      v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v36 = 0;
      v37 = 0;
      v38 = 13;
      v39 = -1;
      v40 = 1134;
      v33 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v33;
    }
    if ( SubscriptionWriteData::IsDirty(v2, EcSubscriptionCommonPassword)
      && !SubscriptionWriteData::IsCleared(v2, (enum _EC_SUBSCRIPTION_PROPERTY_ID)v25) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 13);
      }
      v34 = 0;
      v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v36 = 0;
      v37 = 0;
      v38 = 13;
      v39 = -1;
      v40 = 1140;
      v33 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v33;
    }
  }
  LOBYTE(v25) = 1;
  std::wstring::_Tidy(&pExceptionObject, v25, 0);
  LOBYTE(v31) = 1;
  std::wstring::_Tidy(String1, v31, 0);
  return v20;
}

```

## disassembly

```asm
0x180017b8c  mov     [rsp-8+arg_8], rbx
0x180017b91  mov     [rsp-8+arg_10], rsi
0x180017b96  push    rbp
0x180017b97  push    rdi
0x180017b98  push    r13
0x180017b9a  push    r14
0x180017b9c  push    r15
0x180017b9e  lea     rbp, [rsp-37h]
0x180017ba3  sub     rsp, 0C0h
0x180017baa  mov     rax, cs:__security_cookie
0x180017bb1  xor     rax, rsp
0x180017bb4  mov     [rbp+57h+var_28], rax
0x180017bb8  mov     rsi, rcx
0x180017bbb  mov     edi, 7
0x180017bc0  mov     [rbp+57h+var_30], rdi
0x180017bc4  xor     r14d, r14d
0x180017bc7  mov     [rbp+57h+var_38], r14
0x180017bcb  mov     word ptr [rbp+57h+String1], r14w
0x180017bd0  lea     rbx, [rcx+18h]
0x180017bd4  mov     edx, edi; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x180017bd6  mov     rcx, rbx; this
0x180017bd9  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180017bde  test    al, al
0x180017be0  jz      short loc_180017BFC
0x180017be2  mov     rcx, rbx; this
0x180017be5  call    ?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180017bea  test    al, al
0x180017bec  jnz     short loc_180017BFC
0x180017bee  lea     rdx, [rbp+57h+String1]
0x180017bf2  mov     rcx, rbx
0x180017bf5  call    ?GetURI@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetURI(std::wstring &)
0x180017bfa  jmp     short loc_180017C1E
0x180017bfc  mov     edx, edi; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x180017bfe  mov     rcx, rbx; this
0x180017c01  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180017c06  test    al, al
0x180017c08  jnz     short loc_180017C43
0x180017c0a  lea     r8, [rbp+57h+String1]
0x180017c0e  lea     rdx, aUri; "URI"
0x180017c15  mov     rcx, [rsi+10h]
0x180017c19  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x180017c1e  cmp     [rbp+57h+var_38], r14
0x180017c22  jbe     short loc_180017C43
0x180017c24  lea     rcx, [rbp+57h+String1]
0x180017c28  cmp     [rbp+57h+var_30], 8
0x180017c2d  cmovnb  rcx, [rbp+57h+String1]; String1
0x180017c32  lea     rdx, aHttpSchemasMic_0; "http://schemas.microsoft.com/wbem/wsman"...
0x180017c39  call    cs:__imp__wcsicmp
0x180017c3f  test    eax, eax
0x180017c41  jnz     short loc_180017CBE
0x180017c43  mov     [rbp+57h+var_68], rdi
0x180017c47  mov     [rbp+57h+var_70], r14
0x180017c4b  mov     word ptr [rbp+57h+pExceptionObject], r14w
0x180017c50  mov     r9d, 0Ah
0x180017c56  mov     edx, r9d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x180017c59  mov     rcx, rbx; this
0x180017c5c  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180017c61  test    al, al
0x180017c63  jz      short loc_180017C7F
0x180017c65  mov     rcx, rbx; this
0x180017c68  call    ?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180017c6d  test    al, al
0x180017c6f  jnz     short loc_180017C7F
0x180017c71  lea     rdx, [rbp+57h+pExceptionObject]
0x180017c75  mov     rcx, rbx
0x180017c78  call    ?GetQuery@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetQuery(std::wstring &)
0x180017c7d  jmp     short loc_180017CA6
0x180017c7f  mov     edx, r9d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x180017c82  mov     rcx, rbx; this
0x180017c85  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180017c8a  test    al, al
0x180017c8c  jnz     loc_180018962
0x180017c92  lea     r8, [rbp+57h+pExceptionObject]
0x180017c96  lea     rdx, aQuery_0; "Query"
0x180017c9d  mov     rcx, [rsi+10h]
0x180017ca1  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x180017ca6  cmp     [rbp+57h+var_70], r14
0x180017caa  jz      loc_180018962
0x180017cb0  xor     r8d, r8d
0x180017cb3  mov     dl, 1
0x180017cb5  lea     rcx, [rbp+57h+pExceptionObject]
0x180017cb9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180017cbe  mov     edx, 9; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x180017cc3  mov     rcx, rbx; this
0x180017cc6  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180017ccb  test    al, al
0x180017ccd  jz      loc_180017D87
0x180017cd3  mov     rcx, rbx; this
0x180017cd6  call    ?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180017cdb  test    al, al
0x180017cdd  jnz     loc_180017D87
0x180017ce3  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], r14
0x180017ce7  lea     r8, [rbp+57h+FileTime2]; struct _FILETIME *
0x180017ceb  mov     rcx, [rbx]; struct tag_EcRpcMetadataPropertyList *
0x180017cee  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAU_FILETIME@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,_FILETIME &)
0x180017cf3  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x180017cf7  lea     rcx, FileTime1; lpFileTime1
0x180017cfe  call    cs:__imp_CompareFileTime
0x180017d04  cmp     eax, 0FFFFFFFFh
0x180017d07  jnz     short loc_180017D87
0x180017d09  lea     rax, WPP_GLOBAL_Control
0x180017d10  mov     ebx, 57h ; 'W'
0x180017d15  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d1c  cmp     rcx, rax
0x180017d1f  jz      short loc_180017D43
0x180017d21  test    byte ptr [rcx+1Ch], 40h
0x180017d25  jz      short loc_180017D43
0x180017d27  cmp     byte ptr [rcx+19h], 2
0x180017d2b  jb      short loc_180017D43
0x180017d2d  lea     edx, [rbx-37h]
0x180017d30  mov     r9d, ebx
0x180017d33  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x180017d3a  mov     rcx, [rcx+10h]
0x180017d3e  call    WPP_SF_D
0x180017d43  mov     [rbp+57h+var_78], r14b
0x180017d47  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x180017d4e  mov     [rbp+57h+var_70], rax
0x180017d52  mov     [rbp+57h+var_68], r14
0x180017d56  mov     [rbp+57h+var_60], r14
0x180017d5a  mov     [rbp+57h+var_58], ebx
0x180017d5d  mov     [rbp+57h+var_54], 0FFFFFFFFh
0x180017d64  mov     [rbp+57h+var_50], 3F8h
0x180017d6b  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180017d72  mov     [rbp+57h+pExceptionObject], rax
0x180017d76  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180017d7d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180017d81  call    _CxxThrowException_0
0x180017d87  mov     edx, 11h; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x180017d8c  mov     rcx, rbx; this
0x180017d8f  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180017d94  test    al, al
0x180017d96  jz      loc_180017E88
0x180017d9c  mov     rcx, rbx; this
0x180017d9f  call    ?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180017da4  test    al, al
0x180017da6  jnz     loc_180017E88
0x180017dac  mov     [rbp+57h+var_68], rdi
0x180017db0  mov     [rbp+57h+var_70], r14
0x180017db4  mov     word ptr [rbp+57h+pExceptionObject], r14w
0x180017db9  lea     rdx, [rbp+57h+pExceptionObject]
0x180017dbd  mov     rcx, rbx
0x180017dc0  call    ?GetLocale@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetLocale(std::wstring &)
0x180017dc5  cmp     [rbp+57h+var_70], r14
0x180017dc9  jbe     loc_180017E7A
0x180017dcf  lea     rcx, [rbp+57h+pExceptionObject]
0x180017dd3  cmp     [rbp+57h+var_68], 8
0x180017dd8  cmovnb  rcx, [rbp+57h+pExceptionObject]; lpName
0x180017ddd  xor     edx, edx; dwFlags
0x180017ddf  call    cs:__imp_LocaleNameToLCID
0x180017de5  test    eax, eax
0x180017de7  jnz     loc_180017E7A
0x180017ded  call    cs:__imp_GetLastError
0x180017df3  mov     ebx, eax
0x180017df5  mov     eax, 507h
0x180017dfa  test    ebx, ebx
0x180017dfc  cmovz   ebx, eax
0x180017dff  lea     rax, WPP_GLOBAL_Control
0x180017e06  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e0d  cmp     rcx, rax
0x180017e10  jz      short loc_180017E36
0x180017e12  test    byte ptr [rcx+1Ch], 40h
0x180017e16  jz      short loc_180017E36
0x180017e18  cmp     byte ptr [rcx+19h], 2
0x180017e1c  jb      short loc_180017E36
0x180017e1e  mov     edx, 21h ; '!'
0x180017e23  mov     r9d, ebx
0x180017e26  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x180017e2d  mov     rcx, [rcx+10h]
0x180017e31  call    WPP_SF_D
0x180017e36  mov     [rbp+57h+var_B8], r14b
0x180017e3a  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x180017e41  mov     [rbp+57h+var_B0], rax
0x180017e45  mov     [rbp+57h+var_A8], r14
0x180017e49  mov     [rbp+57h+var_A0], r14
0x180017e4d  mov     [rbp+57h+var_98], ebx
0x180017e50  mov     [rbp+57h+var_94], 0FFFFFFFFh
0x180017e57  mov     [rbp+57h+var_90], 406h
0x180017e5e  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180017e65  mov     [rbp+57h+var_C0], rax
0x180017e69  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180017e70  lea     rcx, [rbp+57h+var_C0]; pExceptionObject
0x180017e74  call    _CxxThrowException_0
0x180017e7a  xor     r8d, r8d
0x180017e7d  mov     dl, 1
0x180017e7f  lea     rcx, [rbp+57h+pExceptionObject]
0x180017e83  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180017e88  mov     r15d, 0Dh
0x180017e8e  mov     edx, r15d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x180017e91  mov     rcx, rbx; this
0x180017e94  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180017e99  test    al, al
0x180017e9b  jz      loc_180017F47
0x180017ea1  mov     rcx, rbx; this
0x180017ea4  call    ?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180017ea9  test    al, al
0x180017eab  jnz     loc_180017F47
0x180017eb1  mov     rcx, rbx; this
0x180017eb4  call    ?GetDeliveryMode@SubscriptionReadData@@QEBA?AW4_EC_SUBSCRIPTION_DELIVERY_MODE@@XZ; SubscriptionReadData::GetDeliveryMode(void)
0x180017eb9  mov     edx, eax; unsigned int
0x180017ebb  lea     rcx, ?EnumNameValueDeliveryMode@@3PAU_ENUM_NAMEVALUE_PAIR@@A; struct _ENUM_NAMEVALUE_PAIR *
0x180017ec2  call    ?EnumValueToName@@YAPEBGPEAU_ENUM_NAMEVALUE_PAIR@@K@Z; EnumValueToName(_ENUM_NAMEVALUE_PAIR *,ulong)
0x180017ec7  test    rax, rax
0x180017eca  jnz     short loc_180017F47
0x180017ecc  lea     rax, WPP_GLOBAL_Control
0x180017ed3  mov     rcx, cs:WPP_GLOBAL_Control
0x180017eda  cmp     rcx, rax
0x180017edd  jz      short loc_180017F02
0x180017edf  test    byte ptr [rcx+1Ch], 40h
0x180017ee3  jz      short loc_180017F02
0x180017ee5  cmp     byte ptr [rcx+19h], 2
0x180017ee9  jb      short loc_180017F02
0x180017eeb  lea     edx, [r15+15h]
0x180017eef  mov     r9d, r15d
0x180017ef2  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x180017ef9  mov     rcx, [rcx+10h]
0x180017efd  call    WPP_SF_D
0x180017f02  mov     [rbp+57h+var_B8], r14b
0x180017f06  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x180017f0d  mov     [rbp+57h+var_B0], rax
0x180017f11  mov     [rbp+57h+var_A8], r14
0x180017f15  mov     [rbp+57h+var_A0], r14
0x180017f19  mov     [rbp+57h+var_98], r15d
0x180017f1d  mov     [rbp+57h+var_94], 0FFFFFFFFh
0x180017f24  mov     [rbp+57h+var_90], 40Dh
0x180017f2b  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180017f32  mov     [rbp+57h+var_C0], rax
0x180017f36  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180017f3d  lea     rcx, [rbp+57h+var_C0]; pExceptionObject
0x180017f41  call    _CxxThrowException_0
0x180017f47  mov     r9d, 12h
0x180017f4d  mov     edx, r9d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x180017f50  mov     rcx, rbx; this
0x180017f53  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180017f58  test    al, al
0x180017f5a  jz      loc_180018016
0x180017f60  mov     rcx, rbx; this
0x180017f63  call    ?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180017f68  test    al, al
0x180017f6a  jnz     loc_180018016
0x180017f70  mov     [rbp+57h+FileTime2.dwLowDateTime], 2
0x180017f77  lea     r8, [rbp+57h+FileTime2]; unsigned int *
0x180017f7b  mov     edx, r9d; unsigned int
0x180017f7e  mov     rcx, [rbx]; struct tag_EcRpcMetadataPropertyList *
0x180017f81  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)
0x180017f86  mov     edx, [rbp+57h+FileTime2.dwLowDateTime]; unsigned int
0x180017f89  lea     rcx, ?EnumNameValueContentFormat@@3PAU_ENUM_NAMEVALUE_PAIR@@A; struct _ENUM_NAMEVALUE_PAIR *
0x180017f90  call    ?EnumValueToName@@YAPEBGPEAU_ENUM_NAMEVALUE_PAIR@@K@Z; EnumValueToName(_ENUM_NAMEVALUE_PAIR *,ulong)
0x180017f95  test    rax, rax
0x180017f98  jnz     short loc_180018016
0x180017f9a  lea     rax, WPP_GLOBAL_Control
0x180017fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180017fa8  cmp     rcx, rax
0x180017fab  jz      short loc_180017FD1
0x180017fad  test    byte ptr [rcx+1Ch], 40h
0x180017fb1  jz      short loc_180017FD1
0x180017fb3  cmp     byte ptr [rcx+19h], 2
0x180017fb7  jb      short loc_180017FD1
0x180017fb9  mov     edx, 23h ; '#'
0x180017fbe  mov     r9d, r15d
0x180017fc1  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x180017fc8  mov     rcx, [rcx+10h]
0x180017fcc  call    WPP_SF_D
0x180017fd1  mov     [rbp+57h+var_B8], r14b
0x180017fd5  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x180017fdc  mov     [rbp+57h+var_B0], rax
0x180017fe0  mov     [rbp+57h+var_A8], r14
0x180017fe4  mov     [rbp+57h+var_A0], r14
0x180017fe8  mov     [rbp+57h+var_98], r15d
0x180017fec  mov     [rbp+57h+var_94], 0FFFFFFFFh
0x180017ff3  mov     [rbp+57h+var_90], 412h
0x180017ffa  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180018001  mov     [rbp+57h+var_C0], rax
0x180018005  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001800c  lea     rcx, [rbp+57h+var_C0]; pExceptionObject
0x180018010  call    _CxxThrowException_0
0x180018016  mov     edx, 8; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x18001801b  mov     rcx, rbx; this
0x18001801e  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180018023  test    al, al
0x180018025  jz      loc_1800180E3
0x18001802b  mov     rcx, rbx; this
0x18001802e  call    ?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180018033  test    al, al
0x180018035  jnz     loc_1800180E3
0x18001803b  mov     [rbp+57h+FileTime2.dwLowDateTime], 1
0x180018042  lea     r8, [rbp+57h+FileTime2]; unsigned int *
0x180018046  mov     edx, 8; unsigned int
0x18001804b  mov     rcx, [rbx]; struct tag_EcRpcMetadataPropertyList *
0x18001804e  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)
0x180018053  mov     edx, [rbp+57h+FileTime2.dwLowDateTime]; unsigned int
0x180018056  lea     rcx, ?EnumNameValueConfigurationMode@@3PAU_ENUM_NAMEVALUE_PAIR@@A; struct _ENUM_NAMEVALUE_PAIR *
0x18001805d  call    ?EnumValueToName@@YAPEBGPEAU_ENUM_NAMEVALUE_PAIR@@K@Z; EnumValueToName(_ENUM_NAMEVALUE_PAIR *,ulong)
0x180018062  test    rax, rax
0x180018065  jnz     short loc_1800180E3
0x180018067  lea     rax, WPP_GLOBAL_Control
0x18001806e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018075  cmp     rcx, rax
0x180018078  jz      short loc_18001809E
0x18001807a  test    byte ptr [rcx+1Ch], 40h
0x18001807e  jz      short loc_18001809E
  ... truncated ...
```
