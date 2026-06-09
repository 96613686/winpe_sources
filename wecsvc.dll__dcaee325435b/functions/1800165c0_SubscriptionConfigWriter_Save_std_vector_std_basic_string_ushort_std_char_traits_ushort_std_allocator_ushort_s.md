# SubscriptionConfigWriter::Save(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x1800165c0`
- end: `0x180017183`
- name: `?Save@SubscriptionConfigWriter@@QEAAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0@Z`
- size: `3011`
- prototype: `__int64 __fastcall(HKEY *this)`
- caller_count: `1`
- callee_count: `39`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004b80`

## callees

- `0x180002510`
- `0x180004288`
- `0x1800062d4`
- `0x180006334`
- `0x18000669c`
- `0x1800128c0`
- `0x1800129f0`
- `0x1800159e0`
- `0x180015acc`
- `0x18001632c`
- `0x180016358`
- `0x1800165c0`
- `0x18001718c`
- `0x180017510`
- `0x18001764c`
- `0x180017b8c`
- `0x180018bd4`
- `0x180018cdc`
- `0x18001dd2c`
- `0x18001dd6c`
- `0x18001ddac`
- `0x18001ddec`
- `0x18001de2c`
- `0x18001de6c`
- `0x18001dec4`
- `0x18001df04`
- `0x18001e08c`
- `0x18001e0cc`
- `0x18001e10c`
- `0x18001e14c`
- `0x18001e18c`
- `0x18001e1cc`
- `0x18001e20c`
- `0x18001e660`
- `0x18001e734`
- `0x18001e808`
- `0x18001f000`
- `0x18001fb3c`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180016df0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180016df0`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001684a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001684a`

## string_xrefs

- `0x180016de5`: `CommonUserName`
- `0x180016e28`: `CommonUserName`
- `0x180016e3d`: `CommonUserName`
- `0x180016dce`: `CommonPassword`
- `0x180016f24`: `ReadExistingEvents`
- `0x180016f62`: `ReadExistingEvents`
- `0x1800167a4`: `ConfigurationMode`
- `0x1800167e4`: `ConfigurationMode`
- `0x1800170fb`: `AllowedSourceDomainComputers`
- `0x180017137`: `AllowedSourceDomainComputers`

## pseudocode

```c
__int64 __fastcall SubscriptionConfigWriter::Save(HKEY *this)
{
  const struct tag_EcRpcMetadataPropertyList **v2; // rbx
  const unsigned __int16 *v3; // r8
  const unsigned __int16 *v4; // r8
  unsigned int v5; // edx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v6; // r9d
  unsigned int v7; // edx
  unsigned int v8; // r8d
  const unsigned __int16 *v9; // r8
  enum _EC_SUBSCRIPTION_PROPERTY_ID v10; // r9d
  const unsigned __int16 *v11; // r8
  enum _EC_SUBSCRIPTION_PROPERTY_ID v12; // r9d
  const unsigned __int16 *v13; // r8
  enum _EC_SUBSCRIPTION_PROPERTY_ID v14; // r9d
  unsigned int v15; // edx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v16; // r9d
  const unsigned __int16 *v17; // r8
  enum _EC_SUBSCRIPTION_DELIVERY_MODE DeliveryMode; // eax
  enum _EC_SUBSCRIPTION_PROPERTY_ID v19; // r9d
  unsigned int v20; // edx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v21; // r9d
  unsigned int v22; // edx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v23; // r9d
  unsigned int v24; // edx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v25; // r9d
  unsigned int v26; // edx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v27; // r9d
  const unsigned __int16 *v28; // r8
  enum _EC_SUBSCRIPTION_PROPERTY_ID v29; // r9d
  const unsigned __int16 *v30; // r8
  enum _EC_SUBSCRIPTION_PROPERTY_ID v31; // r9d
  const unsigned __int16 *v32; // r8
  enum _EC_SUBSCRIPTION_PROPERTY_ID v33; // r9d
  const unsigned __int16 *v34; // r8
  enum _EC_SUBSCRIPTION_PROPERTY_ID v35; // r9d
  unsigned int v36; // edx
  bool IsDirty; // al
  HKEY v38; // rcx
  const unsigned __int16 *v39; // r8
  enum _EC_SUBSCRIPTION_PROPERTY_ID v40; // r9d
  const unsigned __int16 *v41; // r8
  enum _EC_SUBSCRIPTION_PROPERTY_ID v42; // r9d
  unsigned int v43; // edx
  enum _EC_SUBSCRIPTION_PROPERTY_ID v44; // edx
  unsigned int v45; // r9d
  enum _EC_SUBSCRIPTION_PROPERTY_ID v46; // r9d
  const unsigned __int16 *v47; // r8
  enum _EC_SUBSCRIPTION_PROPERTY_ID v48; // r9d
  const unsigned __int16 *v49; // r8
  enum _EC_SUBSCRIPTION_PROPERTY_ID v50; // r9d
  const unsigned __int16 *v51; // r8
  enum _EC_SUBSCRIPTION_PROPERTY_ID v52; // r9d
  __int64 v53; // rdx
  const unsigned __int16 *v54; // r8
  __int64 v55; // rdx
  bool v57; // [rsp+30h] [rbp-A9h] BYREF
  FILETIME FileTime; // [rsp+38h] [rbp-A1h] BYREF
  _BYTE v59[8]; // [rsp+40h] [rbp-99h] BYREF
  __int64 (__fastcall *v60)(); // [rsp+48h] [rbp-91h]
  struct _SYSTEMTIME *p_SystemTime; // [rsp+50h] [rbp-89h]
  unsigned __int16 *v62[2]; // [rsp+58h] [rbp-81h] BYREF
  __int64 v63; // [rsp+68h] [rbp-71h]
  unsigned __int64 v64; // [rsp+70h] [rbp-69h]
  unsigned __int16 *v65[2]; // [rsp+78h] [rbp-61h] BYREF
  __int64 v66; // [rsp+88h] [rbp-51h]
  unsigned __int64 v67; // [rsp+90h] [rbp-49h]
  struct _SYSTEMTIME SystemTime; // [rsp+98h] [rbp-41h] BYREF
  __int64 v69; // [rsp+A8h] [rbp-31h]
  unsigned __int16 v70[32]; // [rsp+B0h] [rbp-29h] BYREF

  v64 = 7;
  v63 = 0;
  LOWORD(v62[0]) = 0;
  SubscriptionConfigWriter::Validate((SubscriptionConfigWriter *)this);
  v2 = (const struct tag_EcRpcMetadataPropertyList **)(this + 3);
  if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), EcSubscriptionEnabled) )
  {
    SubscriptionConfigReader::GetEnabled((SubscriptionConfigReader *)this, &v57);
    if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionEnabled) )
    {
      ConfigBase::DeleteRegValue((ConfigBase *)this, L"Enabled");
    }
    else
    {
      v57 = 0;
      ReadMetadataProp(*v2, 0, &v57);
      if ( !v57 )
        SubscriptionConfigWriter::SetAllExistingBookmarksToFuture((SubscriptionConfigWriter *)this);
      v57 = 0;
      ReadMetadataProp(*v2, 0, &v57);
      RegWriteDWORDValue(this[2], L"Enabled", v57);
    }
  }
  if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), EcSubscriptionEventSourceAddress) )
    SubscriptionConfigWriter::SaveEventSources((SubscriptionConfigReader *)this);
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionDescription) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"Description");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), EcSubscriptionDescription) )
  {
    std::wstring::assign(v62, &word_180026AD8);
    ReadMetadataProp(*v2, 6, v62);
    v3 = (const unsigned __int16 *)v62;
    if ( v64 >= 8 )
      v3 = v62[0];
    ConfigBase::WriteRegStringValue((ConfigBase *)this, L"Description", v3);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionURI) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"URI");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), EcSubscriptionURI) )
  {
    SubscriptionReadData::GetURI(this + 3, v62);
    v4 = (const unsigned __int16 *)v62;
    if ( v64 >= 8 )
      v4 = v62[0];
    ConfigBase::WriteRegStringValue((ConfigBase *)this, L"URI", v4);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionConfigurationMode) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"ConfigurationMode");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), EcSubscriptionConfigurationMode) )
  {
    FileTime.dwLowDateTime = 1;
    ReadMetadataProp(*v2, v5, (unsigned int *)&FileTime);
    ConfigBase::WriteRegEnumValue(
      (ConfigBase *)this,
      L"ConfigurationMode",
      (struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueConfigurationMode,
      FileTime.dwLowDateTime);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionExpires) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"Expires");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v6) )
  {
    FileTime = 0;
    ReadMetadataProp(*v2, v7, &FileTime);
    SystemTime = 0;
    FileTimeToSystemTime(&FileTime, &SystemTime);
    SystemTimeToString(&SystemTime, v70, v8, &FileTime);
    std::wstring::assign(v62, v70);
    v9 = (const unsigned __int16 *)v62;
    if ( v64 >= 8 )
      v9 = v62[0];
    ConfigBase::WriteRegStringValue((ConfigBase *)this, L"Expires", v9);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionDialect) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"Dialect");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v10) )
  {
    SubscriptionReadData::GetDialect(this + 3, v62);
    v11 = (const unsigned __int16 *)v62;
    if ( v64 >= 8 )
      v11 = v62[0];
    ConfigBase::WriteRegStringValue((ConfigBase *)this, L"Dialect", v11);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionQuery) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"Query");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v12) )
  {
    SubscriptionReadData::GetQuery(this + 3, v62);
    v13 = (const unsigned __int16 *)v62;
    if ( v64 >= 8 )
      v13 = v62[0];
    ConfigBase::WriteRegStringValue((ConfigBase *)this, L"Query", v13);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionTransportPort) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"TransportPort");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v14) )
  {
    FileTime.dwLowDateTime = 0;
    ReadMetadataProp(*v2, v15, (unsigned int *)&FileTime);
    RegWriteDWORDValue(this[2], L"TransportPort", FileTime.dwLowDateTime);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionTransportName) )
    goto LABEL_53;
  if ( !SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v16) )
    goto LABEL_54;
  SubscriptionReadData::GetTransportName(this + 3, v62);
  if ( !v63 )
  {
LABEL_53:
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"TransportName");
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"TransportPort");
  }
  else
  {
    v17 = (const unsigned __int16 *)v62;
    if ( v64 >= 8 )
      v17 = v62[0];
    ConfigBase::WriteRegStringValue((ConfigBase *)this, L"TransportName", v17);
  }
LABEL_54:
  if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), EcSubscriptionDeliveryMode) )
  {
    DeliveryMode = SubscriptionReadData::GetDeliveryMode((SubscriptionReadData *)(this + 3));
    ConfigBase::WriteRegEnumValue(
      (ConfigBase *)this,
      L"DeliveryMode",
      (struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueDeliveryMode,
      DeliveryMode);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionDeliveryMaxItems) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"MaxItems");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v19) )
  {
    FileTime.dwLowDateTime = -1;
    ReadMetadataProp(*v2, v20, (unsigned int *)&FileTime);
    RegWriteDWORDValue(this[2], L"MaxItems", FileTime.dwLowDateTime);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionDeliveryMaxLatencyTime) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"MaxLatencyTime");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v21) )
  {
    FileTime.dwLowDateTime = 15000;
    ReadMetadataProp(*v2, v22, (unsigned int *)&FileTime);
    RegWriteDWORDValue(this[2], L"MaxLatencyTime", FileTime.dwLowDateTime);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionContentFormat) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"ContentFormat");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v23) )
  {
    FileTime.dwLowDateTime = 2;
    ReadMetadataProp(*v2, v24, (unsigned int *)&FileTime);
    ConfigBase::WriteRegEnumValue(
      (ConfigBase *)this,
      L"ContentFormat",
      (struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueContentFormat,
      FileTime.dwLowDateTime);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionHeartbeatInterval) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"HeartBeatInterval");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v25) )
  {
    FileTime.dwLowDateTime = 900000;
    ReadMetadataProp(*v2, v26, (unsigned int *)&FileTime);
    RegWriteDWORDValue(this[2], L"HeartBeatInterval", FileTime.dwLowDateTime);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionLocale) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"Locale");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v27) )
  {
    SubscriptionReadData::GetLocale(this + 3, v62);
    v28 = (const unsigned __int16 *)v62;
    if ( v64 >= 8 )
      v28 = v62[0];
    ConfigBase::WriteRegStringValue((ConfigBase *)this, L"Locale", v28);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionLogFile) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"LogFile");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v29) )
  {
    SubscriptionReadData::GetLogFile(this + 3, v62);
    v30 = (const unsigned __int16 *)v62;
    if ( v64 >= 8 )
      v30 = v62[0];
    ConfigBase::WriteRegStringValue((ConfigBase *)this, L"LogFile", v30);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionPublisherName) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"PublisherName");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v31) )
  {
    SubscriptionReadData::GetPublisherName(this + 3, v62);
    v32 = (const unsigned __int16 *)v62;
    if ( v64 >= 8 )
      v32 = v62[0];
    ConfigBase::WriteRegStringValue((ConfigBase *)this, L"PublisherName", v32);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionHostName) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"HostName");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v33) )
  {
    SubscriptionReadData::GetHostName(this + 3, v62);
    v34 = (const unsigned __int16 *)v62;
    if ( v64 >= 8 )
      v34 = v62[0];
    ConfigBase::WriteRegStringValue((ConfigBase *)this, L"HostName", v34);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionCredentialsType) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"CredentialsType");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v35) )
  {
    FileTime.dwLowDateTime = 0;
    ReadMetadataProp(*v2, v36, (unsigned int *)&FileTime);
    ConfigBase::WriteRegEnumValue(
      (ConfigBase *)this,
      L"CredentialsType",
      (struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueCredentialsType,
      FileTime.dwLowDateTime);
  }
  v67 = 7;
  v66 = 0;
  LOWORD(v65[0]) = 0;
  IsDirty = SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), EcSubscriptionCommonUserName);
  v38 = this[2];
  if ( IsDirty )
  {
    SubscriptionConfigWriter::DeletePassword(v38, L"CommonPassword");
    RegDeleteValueW(this[2], L"CommonUserName");
    if ( !SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionCommonUserName) )
    {
      SubscriptionReadData::GetCommonUserName(this + 3, v65);
      if ( !v66 )
        goto LABEL_118;
      v39 = (const unsigned __int16 *)v65;
      if ( v67 >= 8 )
        v39 = v65[0];
      ConfigBase::WriteRegStringValue((ConfigBase *)this, L"CommonUserName", v39);
    }
  }
  else
  {
    RegReadStringValue(v38, L"CommonUserName", v65);
  }
  if ( v66 )
  {
    if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionCommonPassword) )
    {
      SubscriptionConfigWriter::DeletePassword(this[2], L"CommonPassword");
    }
    else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v40) )
    {
      SystemTime = 0;
      v69 = 0;
      SubscriptionReadData::GetCommonPassword(this + 3, &SystemTime);
      v59[0] = 0;
      v60 = ZeroPasswordString;
      p_SystemTime = &SystemTime;
      if ( *(_QWORD *)&SystemTime.wHour == *(_QWORD *)&SystemTime.wYear || !**(_WORD **)&SystemTime.wYear )
      {
        SubscriptionConfigWriter::DeletePassword(this[2], L"CommonPassword");
      }
      else
      {
        v41 = (const unsigned __int16 *)v65;
        if ( v67 >= 8 )
          v41 = v65[0];
        SubscriptionConfigWriter::SavePassword(
          *(SubscriptionConfigWriter **)&SystemTime.wYear,
          this[2],
          v41,
          L"CommonPassword",
          *(const unsigned __int16 **)&SystemTime.wYear);
      }
      wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v59);
      std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(&SystemTime);
    }
  }
LABEL_118:
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionReadExistingEvents) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"ReadExistingEvents");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v42) )
  {
    v57 = 0;
    ReadMetadataProp(*v2, v43, &v57);
    RegWriteDWORDValue(this[2], L"ReadExistingEvents", v57);
  }
  if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), EcSubscriptionType)
    && !SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), v44) )
  {
    FileTime.dwLowDateTime = 1;
    ReadMetadataProp(*v2, v45, (unsigned int *)&FileTime);
    ConfigBase::WriteRegEnumValue(
      (ConfigBase *)this,
      L"SubscriptionType",
      (struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueSubscriptionType,
      FileTime.dwLowDateTime);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionAllowedIssuerCAs) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"AllowedIssuerCAs");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v46) )
  {
    SubscriptionReadData::GetAllowedIssuerCAs(this + 3, v62);
    v47 = (const unsigned __int16 *)v62;
    if ( v64 >= 8 )
      v47 = v62[0];
    ConfigBase::WriteRegStringValue((ConfigBase *)this, L"AllowedIssuerCAs", v47);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionAllowedSubjects) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"AllowedSubjects");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v48) )
  {
    SubscriptionReadData::GetAllowedSubjects(this + 3, v62);
    v49 = (const unsigned __int16 *)v62;
    if ( v64 >= 8 )
      v49 = v62[0];
    ConfigBase::WriteRegStringValue((ConfigBase *)this, L"AllowedSubjects", v49);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionDeniedSubjects) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"DeniedSubjects");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v50) )
  {
    SubscriptionReadData::GetDeniedSubjects(this + 3, v62);
    v51 = (const unsigned __int16 *)v62;
    if ( v64 >= 8 )
      v51 = v62[0];
    ConfigBase::WriteRegStringValue((ConfigBase *)this, L"DeniedSubjects", v51);
  }
  if ( SubscriptionWriteData::IsCleared((SubscriptionWriteData *)(this + 3), EcSubscriptionAllowedSourceDomainComputers) )
  {
    ConfigBase::DeleteRegValue((ConfigBase *)this, L"AllowedSourceDomainComputers");
  }
  else if ( SubscriptionWriteData::IsDirty((SubscriptionWriteData *)(this + 3), v52) )
  {
    SubscriptionReadData::GetAllowedSourceDomainComputers(this + 3, v62);
    v54 = (const unsigned __int16 *)v62;
    if ( v64 >= 8 )
      v54 = v62[0];
    ConfigBase::WriteRegStringValue((ConfigBase *)this, L"AllowedSourceDomainComputers", v54);
  }
  LOBYTE(v53) = 1;
  std::wstring::_Tidy(v65, v53, 0);
  LOBYTE(v55) = 1;
  return std::wstring::_Tidy(v62, v55, 0);
}

```

## disassembly

```asm
0x1800165c0  push    rbp
0x1800165c2  push    rbx
0x1800165c3  push    rsi
0x1800165c4  push    rdi
0x1800165c5  push    r12
0x1800165c7  push    r14
0x1800165c9  push    r15
0x1800165cb  lea     rbp, [rsp-27h]
0x1800165d0  sub     rsp, 100h
0x1800165d7  mov     rax, cs:__security_cookie
0x1800165de  xor     rax, rsp
0x1800165e1  mov     [rbp+57h+var_40], rax
0x1800165e5  mov     r14, r8
0x1800165e8  mov     rsi, rdx
0x1800165eb  mov     rdi, rcx
0x1800165ee  mov     [rbp+57h+var_C0], 7
0x1800165f6  xor     r12d, r12d
0x1800165f9  mov     [rbp+57h+var_C8], r12
0x1800165fd  mov     word ptr [rsp+130h+var_D8], r12w
0x180016603  call    ?Validate@SubscriptionConfigWriter@@AEAA?AW4_EC_SUBSCRIPTION_TYPE@@XZ; SubscriptionConfigWriter::Validate(void)
0x180016608  mov     r15d, eax
0x18001660b  lea     rbx, [rdi+18h]
0x18001660f  xor     edx, edx; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x180016611  mov     rcx, rbx; this
0x180016614  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180016619  test    al, al
0x18001661b  jz      short loc_18001669C
0x18001661d  lea     rdx, [rsp+130h+var_100]; bool *
0x180016622  mov     rcx, rdi; this
0x180016625  call    ?GetEnabled@SubscriptionConfigReader@@QEBA_NAEA_N@Z; SubscriptionConfigReader::GetEnabled(bool &)
0x18001662a  xor     edx, edx; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x18001662c  mov     rcx, rbx; this
0x18001662f  call    ?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180016634  test    al, al
0x180016636  jz      short loc_180016649
0x180016638  lea     rdx, aEnabled; "Enabled"
0x18001663f  mov     rcx, rdi; this
0x180016642  call    ?DeleteRegValue@ConfigBase@@IEAA_NPEBG@Z; ConfigBase::DeleteRegValue(ushort const *)
0x180016647  jmp     short loc_18001669C
0x180016649  mov     [rsp+130h+var_100], r12b
0x18001664e  lea     r8, [rsp+130h+var_100]; bool *
0x180016653  xor     edx, edx; unsigned int
0x180016655  mov     rcx, [rbx]; struct tag_EcRpcMetadataPropertyList *
0x180016658  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEA_N@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,bool &)
0x18001665d  cmp     [rsp+130h+var_100], r12b
0x180016662  jnz     short loc_18001666C
0x180016664  mov     rcx, rdi; this
0x180016667  call    ?SetAllExistingBookmarksToFuture@SubscriptionConfigWriter@@AEAAXXZ; SubscriptionConfigWriter::SetAllExistingBookmarksToFuture(void)
0x18001666c  mov     [rsp+130h+var_100], r12b
0x180016671  lea     r8, [rsp+130h+var_100]; bool *
0x180016676  xor     edx, edx; unsigned int
0x180016678  mov     rcx, [rbx]; struct tag_EcRpcMetadataPropertyList *
0x18001667b  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEA_N@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,bool &)
0x180016680  mov     r8d, r12d
0x180016683  cmp     [rsp+130h+var_100], r12b
0x180016688  setnz   r8b; unsigned int
0x18001668c  lea     rdx, aEnabled; "Enabled"
0x180016693  mov     rcx, [rdi+10h]; HKEY
0x180016697  call    ?RegWriteDWORDValue@@YAXPEAUHKEY__@@PEBGK@Z; RegWriteDWORDValue(HKEY__ *,ushort const *,ulong)
0x18001669c  mov     edx, 2; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x1800166a1  mov     rcx, rbx; this
0x1800166a4  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x1800166a9  test    al, al
0x1800166ab  jz      short loc_1800166BE
0x1800166ad  mov     r9, r14
0x1800166b0  mov     r8, rsi
0x1800166b3  mov     edx, r15d
0x1800166b6  mov     rcx, rdi; this
0x1800166b9  call    ?SaveEventSources@SubscriptionConfigWriter@@AEAAXW4_EC_SUBSCRIPTION_TYPE@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z; SubscriptionConfigWriter::SaveEventSources(_EC_SUBSCRIPTION_TYPE,std::vector<std::wstring> &,std::vector<std::wstring> &)
0x1800166be  mov     r14d, 6
0x1800166c4  mov     edx, r14d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x1800166c7  mov     rcx, rbx; this
0x1800166ca  call    ?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)
0x1800166cf  lea     esi, [r14+2]
0x1800166d3  test    al, al
0x1800166d5  jz      short loc_1800166E8
0x1800166d7  lea     rdx, aDescription; "Description"
0x1800166de  mov     rcx, rdi; this
0x1800166e1  call    ?DeleteRegValue@ConfigBase@@IEAA_NPEBG@Z; ConfigBase::DeleteRegValue(ushort const *)
0x1800166e6  jmp     short loc_180016736
0x1800166e8  mov     edx, r14d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x1800166eb  mov     rcx, rbx; this
0x1800166ee  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x1800166f3  test    al, al
0x1800166f5  jz      short loc_180016736
0x1800166f7  lea     rdx, word_180026AD8
0x1800166fe  lea     rcx, [rsp+130h+var_D8]
0x180016703  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180016708  lea     r8, [rsp+130h+var_D8]
0x18001670d  mov     edx, r14d
0x180016710  mov     rcx, [rbx]
0x180016713  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::wstring &)
0x180016718  lea     r8, [rsp+130h+var_D8]
0x18001671d  cmp     [rbp+57h+var_C0], rsi
0x180016721  cmovnb  r8, [rsp+130h+var_D8]; unsigned __int16 *
0x180016727  lea     rdx, aDescription; "Description"
0x18001672e  mov     rcx, rdi; this
0x180016731  call    ?WriteRegStringValue@ConfigBase@@IEBAXPEBG0@Z; ConfigBase::WriteRegStringValue(ushort const *,ushort const *)
0x180016736  mov     r15d, 7
0x18001673c  mov     edx, r15d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x18001673f  mov     rcx, rbx; this
0x180016742  call    ?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180016747  test    al, al
0x180016749  jz      short loc_18001675C
0x18001674b  lea     rdx, aUri; "URI"
0x180016752  mov     rcx, rdi; this
0x180016755  call    ?DeleteRegValue@ConfigBase@@IEAA_NPEBG@Z; ConfigBase::DeleteRegValue(ushort const *)
0x18001675a  jmp     short loc_180016796
0x18001675c  mov     edx, r15d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x18001675f  mov     rcx, rbx; this
0x180016762  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180016767  test    al, al
0x180016769  jz      short loc_180016796
0x18001676b  lea     rdx, [rsp+130h+var_D8]
0x180016770  mov     rcx, rbx
0x180016773  call    ?GetURI@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetURI(std::wstring &)
0x180016778  lea     r8, [rsp+130h+var_D8]
0x18001677d  cmp     [rbp+57h+var_C0], rsi
0x180016781  cmovnb  r8, [rsp+130h+var_D8]; unsigned __int16 *
0x180016787  lea     rdx, aUri; "URI"
0x18001678e  mov     rcx, rdi; this
0x180016791  call    ?WriteRegStringValue@ConfigBase@@IEBAXPEBG0@Z; ConfigBase::WriteRegStringValue(ushort const *,ushort const *)
0x180016796  mov     edx, esi; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x180016798  mov     rcx, rbx; this
0x18001679b  call    ?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)
0x1800167a0  test    al, al
0x1800167a2  jz      short loc_1800167B5
0x1800167a4  lea     rdx, aConfigurationm; "ConfigurationMode"
0x1800167ab  mov     rcx, rdi; this
0x1800167ae  call    ?DeleteRegValue@ConfigBase@@IEAA_NPEBG@Z; ConfigBase::DeleteRegValue(ushort const *)
0x1800167b3  jmp     short loc_1800167F3
0x1800167b5  mov     edx, esi; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x1800167b7  mov     rcx, rbx; this
0x1800167ba  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x1800167bf  test    al, al
0x1800167c1  jz      short loc_1800167F3
0x1800167c3  mov     [rsp+130h+FileTime.dwLowDateTime], 1
0x1800167cb  lea     r8, [rsp+130h+FileTime]; unsigned int *
0x1800167d0  mov     rcx, [rbx]; struct tag_EcRpcMetadataPropertyList *
0x1800167d3  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)
0x1800167d8  mov     r9d, [rsp+130h+FileTime.dwLowDateTime]; unsigned int
0x1800167dd  lea     r8, ?EnumNameValueConfigurationMode@@3PAU_ENUM_NAMEVALUE_PAIR@@A; struct _ENUM_NAMEVALUE_PAIR *
0x1800167e4  lea     rdx, aConfigurationm; "ConfigurationMode"
0x1800167eb  mov     rcx, rdi; this
0x1800167ee  call    ?WriteRegEnumValue@ConfigBase@@IEBAXPEBGPEAU_ENUM_NAMEVALUE_PAIR@@K@Z; ConfigBase::WriteRegEnumValue(ushort const *,_ENUM_NAMEVALUE_PAIR *,ulong)
0x1800167f3  mov     r9d, 9
0x1800167f9  mov     edx, r9d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x1800167fc  mov     rcx, rbx; this
0x1800167ff  call    ?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180016804  test    al, al
0x180016806  jz      short loc_180016819
0x180016808  lea     rdx, aExpires; "Expires"
0x18001680f  mov     rcx, rdi; this
0x180016812  call    ?DeleteRegValue@ConfigBase@@IEAA_NPEBG@Z; ConfigBase::DeleteRegValue(ushort const *)
0x180016817  jmp     short loc_18001688E
0x180016819  mov     edx, r9d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x18001681c  mov     rcx, rbx; this
0x18001681f  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180016824  test    al, al
0x180016826  jz      short loc_18001688E
0x180016828  mov     qword ptr [rsp+130h+FileTime.dwLowDateTime], r12
0x18001682d  lea     r8, [rsp+130h+FileTime]; struct _FILETIME *
0x180016832  mov     rcx, [rbx]; struct tag_EcRpcMetadataPropertyList *
0x180016835  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAU_FILETIME@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,_FILETIME &)
0x18001683a  xorps   xmm0, xmm0
0x18001683d  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180016841  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x180016845  lea     rcx, [rsp+130h+FileTime]; lpFileTime
0x18001684a  call    cs:__imp_FileTimeToSystemTime
0x180016850  lea     r9, [rsp+130h+FileTime]; struct _FILETIME *
0x180016855  lea     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x180016859  lea     rcx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x18001685d  call    ?SystemTimeToString@@YAPEAGAEBU_SYSTEMTIME@@PEAGKPEBU_FILETIME@@@Z; SystemTimeToString(_SYSTEMTIME const &,ushort *,ulong,_FILETIME const *)
0x180016862  lea     rdx, [rbp+57h+var_80]
0x180016866  lea     rcx, [rsp+130h+var_D8]
0x18001686b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180016870  lea     r8, [rsp+130h+var_D8]
0x180016875  cmp     [rbp+57h+var_C0], rsi
0x180016879  cmovnb  r8, [rsp+130h+var_D8]; unsigned __int16 *
0x18001687f  lea     rdx, aExpires; "Expires"
0x180016886  mov     rcx, rdi; this
0x180016889  call    ?WriteRegStringValue@ConfigBase@@IEBAXPEBG0@Z; ConfigBase::WriteRegStringValue(ushort const *,ushort const *)
0x18001688e  mov     r9d, 1Ah
0x180016894  mov     edx, r9d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x180016897  mov     rcx, rbx; this
0x18001689a  call    ?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)
0x18001689f  test    al, al
0x1800168a1  jz      short loc_1800168B4
0x1800168a3  lea     rdx, aDialect; "Dialect"
0x1800168aa  mov     rcx, rdi; this
0x1800168ad  call    ?DeleteRegValue@ConfigBase@@IEAA_NPEBG@Z; ConfigBase::DeleteRegValue(ushort const *)
0x1800168b2  jmp     short loc_1800168EE
0x1800168b4  mov     edx, r9d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x1800168b7  mov     rcx, rbx; this
0x1800168ba  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x1800168bf  test    al, al
0x1800168c1  jz      short loc_1800168EE
0x1800168c3  lea     rdx, [rsp+130h+var_D8]
0x1800168c8  mov     rcx, rbx
0x1800168cb  call    ?GetDialect@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetDialect(std::wstring &)
0x1800168d0  lea     r8, [rsp+130h+var_D8]
0x1800168d5  cmp     [rbp+57h+var_C0], rsi
0x1800168d9  cmovnb  r8, [rsp+130h+var_D8]; unsigned __int16 *
0x1800168df  lea     rdx, aDialect; "Dialect"
0x1800168e6  mov     rcx, rdi; this
0x1800168e9  call    ?WriteRegStringValue@ConfigBase@@IEBAXPEBG0@Z; ConfigBase::WriteRegStringValue(ushort const *,ushort const *)
0x1800168ee  mov     r9d, 0Ah
0x1800168f4  mov     edx, r9d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x1800168f7  mov     rcx, rbx; this
0x1800168fa  call    ?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)
0x1800168ff  test    al, al
0x180016901  jz      short loc_180016914
0x180016903  lea     rdx, aQuery_0; "Query"
0x18001690a  mov     rcx, rdi; this
0x18001690d  call    ?DeleteRegValue@ConfigBase@@IEAA_NPEBG@Z; ConfigBase::DeleteRegValue(ushort const *)
0x180016912  jmp     short loc_18001694E
0x180016914  mov     edx, r9d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x180016917  mov     rcx, rbx; this
0x18001691a  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x18001691f  test    al, al
0x180016921  jz      short loc_18001694E
0x180016923  lea     rdx, [rsp+130h+var_D8]
0x180016928  mov     rcx, rbx
0x18001692b  call    ?GetQuery@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetQuery(std::wstring &)
0x180016930  lea     r8, [rsp+130h+var_D8]
0x180016935  cmp     [rbp+57h+var_C0], rsi
0x180016939  cmovnb  r8, [rsp+130h+var_D8]; unsigned __int16 *
0x18001693f  lea     rdx, aQuery_0; "Query"
0x180016946  mov     rcx, rdi; this
0x180016949  call    ?WriteRegStringValue@ConfigBase@@IEBAXPEBG0@Z; ConfigBase::WriteRegStringValue(ushort const *,ushort const *)
0x18001694e  mov     r9d, 0Ch
0x180016954  mov     edx, r9d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x180016957  mov     rcx, rbx; this
0x18001695a  call    ?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)
0x18001695f  lea     r14, aTransportport; "TransportPort"
0x180016966  test    al, al
0x180016968  jz      short loc_180016977
0x18001696a  mov     rdx, r14; unsigned __int16 *
0x18001696d  mov     rcx, rdi; this
0x180016970  call    ?DeleteRegValue@ConfigBase@@IEAA_NPEBG@Z; ConfigBase::DeleteRegValue(ushort const *)
0x180016975  jmp     short loc_1800169A9
0x180016977  mov     edx, r9d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x18001697a  mov     rcx, rbx; this
0x18001697d  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180016982  test    al, al
0x180016984  jz      short loc_1800169A9
0x180016986  mov     [rsp+130h+FileTime.dwLowDateTime], r12d
0x18001698b  lea     r8, [rsp+130h+FileTime]; unsigned int *
0x180016990  mov     rcx, [rbx]; struct tag_EcRpcMetadataPropertyList *
0x180016993  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)
0x180016998  mov     r8d, [rsp+130h+FileTime.dwLowDateTime]; unsigned int
0x18001699d  mov     rdx, r14; unsigned __int16 *
0x1800169a0  mov     rcx, [rdi+10h]; HKEY
0x1800169a4  call    ?RegWriteDWORDValue@@YAXPEAUHKEY__@@PEBGK@Z; RegWriteDWORDValue(HKEY__ *,ushort const *,ulong)
0x1800169a9  mov     r9d, 0Bh
0x1800169af  mov     edx, r9d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x1800169b2  mov     rcx, rbx; this
0x1800169b5  call    ?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)
0x1800169ba  test    al, al
0x1800169bc  jnz     short loc_180016A00
0x1800169be  mov     edx, r9d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x1800169c1  mov     rcx, rbx; this
0x1800169c4  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x1800169c9  test    al, al
0x1800169cb  jz      short loc_180016A1A
0x1800169cd  lea     rdx, [rsp+130h+var_D8]
0x1800169d2  mov     rcx, rbx
0x1800169d5  call    ?GetTransportName@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetTransportName(std::wstring &)
0x1800169da  cmp     [rbp+57h+var_C8], r12
0x1800169de  jz      short loc_180016A00
0x1800169e0  lea     r8, [rsp+130h+var_D8]
0x1800169e5  cmp     [rbp+57h+var_C0], rsi
0x1800169e9  cmovnb  r8, [rsp+130h+var_D8]; unsigned __int16 *
0x1800169ef  lea     rdx, aTransportname; "TransportName"
0x1800169f6  mov     rcx, rdi; this
0x1800169f9  call    ?WriteRegStringValue@ConfigBase@@IEBAXPEBG0@Z; ConfigBase::WriteRegStringValue(ushort const *,ushort const *)
0x1800169fe  jmp     short loc_180016A1A
0x180016a00  lea     rdx, aTransportname; "TransportName"
0x180016a07  mov     rcx, rdi; this
0x180016a0a  call    ?DeleteRegValue@ConfigBase@@IEAA_NPEBG@Z; ConfigBase::DeleteRegValue(ushort const *)
0x180016a0f  mov     rdx, r14; unsigned __int16 *
0x180016a12  mov     rcx, rdi; this
0x180016a15  call    ?DeleteRegValue@ConfigBase@@IEAA_NPEBG@Z; ConfigBase::DeleteRegValue(ushort const *)
0x180016a1a  mov     edx, 0Dh; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x180016a1f  mov     rcx, rbx; this
0x180016a22  call    ?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180016a27  test    al, al
0x180016a29  jz      short loc_180016A4C
0x180016a2b  mov     rcx, rbx; this
0x180016a2e  call    ?GetDeliveryMode@SubscriptionReadData@@QEBA?AW4_EC_SUBSCRIPTION_DELIVERY_MODE@@XZ; SubscriptionReadData::GetDeliveryMode(void)
0x180016a33  mov     r9d, eax; unsigned int
0x180016a36  lea     r8, ?EnumNameValueDeliveryMode@@3PAU_ENUM_NAMEVALUE_PAIR@@A; struct _ENUM_NAMEVALUE_PAIR *
0x180016a3d  lea     rdx, aDeliverymode; "DeliveryMode"
0x180016a44  mov     rcx, rdi; this
0x180016a47  call    ?WriteRegEnumValue@ConfigBase@@IEBAXPEBGPEAU_ENUM_NAMEVALUE_PAIR@@K@Z; ConfigBase::WriteRegEnumValue(ushort const *,_ENUM_NAMEVALUE_PAIR *,ulong)
0x180016a4c  mov     r9d, 0Eh
0x180016a52  mov     edx, r9d; enum _EC_SUBSCRIPTION_PROPERTY_ID
0x180016a55  mov     rcx, rbx; this
0x180016a58  call    ?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z; SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)
0x180016a5d  test    al, al
  ... truncated ...
```
