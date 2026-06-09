# SubscriptionConfigSnapshot::SubscriptionConfigSnapshot(SubscriptionConfigReader const &,ushort const *,tag_EcRpcMetadataPropertyList &,bool,bool,bool)

- ea: `0x18001483c`
- end: `0x18001512c`
- name: `??0SubscriptionConfigSnapshot@@QEAA@AEBVSubscriptionConfigReader@@PEBGAEAUtag_EcRpcMetadataPropertyList@@_N33@Z`
- size: `2288`
- prototype: `SubscriptionConfigSnapshot *__fastcall(SubscriptionConfigSnapshot *this, HKEY *, const unsigned __int16 *, struct tag_EcRpcMetadataPropertyList *, bool, bool, bool)`
- caller_count: `4`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800042d0`
- `0x180004b80`
- `0x1800052cc`
- `0x180005ad0`

## callees

- `0x18000195c`
- `0x180002510`
- `0x1800032dc`
- `0x180003a50`
- `0x180003be8`
- `0x180003cc8`
- `0x180004288`
- `0x1800062d4`
- `0x180006334`
- `0x18000669c`
- `0x180012424`
- `0x1800128c0`
- `0x1800143f8`
- `0x18001483c`
- `0x1800153c0`
- `0x180015dd4`
- `0x180015f78`
- `0x180016098`
- `0x1800161e4`
- `0x180016514`
- `0x18001e5e8`
- `0x18001f0d8`
- `0x18001f198`
- `0x18001f258`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d12`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180014cf1`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180014cf1`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x180014d04`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x180014d04`

## string_xrefs

- `0x180014ea7`: `CommonUserName`
- `0x180014f05`: `CommonPassword`
- `0x180014f67`: `ReadExistingEvents`
- `0x1800148ee`: `ConfigurationMode`
- `0x1800149fc`: `ConfigurationMode`
- `0x18001509e`: `AllowedSourceDomainComputers`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SubscriptionConfigSnapshot *__fastcall SubscriptionConfigSnapshot::SubscriptionConfigSnapshot(
        SubscriptionConfigSnapshot *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        struct tag_EcRpcMetadataPropertyList *a4,
        bool a5,
        bool a6,
        bool a7)
{
  SubscriptionWriteData *v10; // rbx
  bool Enabled; // al
  struct tag_EcRpcMetadataPropertyList *v12; // rdx
  bool v13; // r14
  const unsigned __int16 *v14; // r8
  const unsigned __int16 *v15; // r8
  struct tag_EcRpcMetadataPropertyList *v16; // rdx
  struct tag_EcRpcMetadataPropertyList *v17; // rdx
  const unsigned __int16 *v18; // r8
  const unsigned __int16 *v19; // r8
  const unsigned __int16 *v20; // r8
  struct tag_EcRpcMetadataPropertyList *v21; // rcx
  enum _EC_SUBSCRIPTION_DELIVERY_MODE v22; // edx
  struct tag_EcRpcMetadataPropertyList *v23; // rdx
  struct tag_EcRpcMetadataPropertyList *v24; // rdx
  struct tag_EcRpcMetadataPropertyList *v25; // rdx
  bool RegEnumValue; // al
  enum _EC_SUBSCRIPTION_CONTENT_FORMAT v27; // edx
  unsigned __int16 **v28; // rcx
  LCID ThreadLocale; // eax
  DWORD LastError; // ebx
  const unsigned __int16 *v31; // r8
  unsigned __int16 **v32; // rcx
  const unsigned __int16 *v33; // r8
  const unsigned __int16 *v34; // r8
  struct tag_EcRpcMetadataPropertyList *v35; // rdx
  __int64 v36; // rax
  struct tag_EcRpcMetadataPropertyList *v37; // rcx
  __int64 v38; // rcx
  const unsigned __int16 *v39; // r8
  const unsigned __int16 *v40; // r8
  struct tag_EcRpcMetadataPropertyList *v41; // rdx
  __int64 v42; // rax
  struct tag_EcRpcMetadataPropertyList *v43; // rcx
  struct tag_EcRpcMetadataPropertyList *v44; // rdx
  __int64 v45; // rax
  struct tag_EcRpcMetadataPropertyList *v46; // rcx
  const unsigned __int16 *v47; // r8
  const unsigned __int16 *v48; // r8
  const unsigned __int16 *v49; // r8
  const unsigned __int16 *v50; // r8
  __int64 v51; // rdx
  _EC_SUBSCRIPTION_DELIVERY_MODE v53; // [rsp+20h] [rbp-E0h] BYREF
  bool v54; // [rsp+24h] [rbp-DCh] BYREF
  _EC_SUBSCRIPTION_CONFIGURATION_MODE v55; // [rsp+28h] [rbp-D8h] BYREF
  struct _FILETIME v56; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v57[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v58; // [rsp+48h] [rbp-B8h]
  _BYTE v59[16]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v60; // [rsp+60h] [rbp-A0h]
  int v61; // [rsp+68h] [rbp-98h]
  void **pExceptionObject; // [rsp+70h] [rbp-90h] BYREF
  char v63; // [rsp+78h] [rbp-88h]
  const char *v64; // [rsp+80h] [rbp-80h]
  __int64 v65; // [rsp+88h] [rbp-78h]
  __int64 v66; // [rsp+90h] [rbp-70h]
  DWORD v67; // [rsp+98h] [rbp-68h]
  int v68; // [rsp+9Ch] [rbp-64h]
  int v69; // [rsp+A0h] [rbp-60h]
  _BYTE v70[8]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 (__fastcall *v71)(); // [rsp+B0h] [rbp-50h]
  unsigned __int16 **v72; // [rsp+B8h] [rbp-48h]
  SubscriptionConfigSnapshot *v73; // [rsp+C0h] [rbp-40h]
  _BYTE v74[128]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v75[2]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v76; // [rsp+160h] [rbp+60h]
  unsigned __int64 v77; // [rsp+168h] [rbp+68h]
  WCHAR Name[88]; // [rsp+170h] [rbp+70h] BYREF

  v73 = this;
  *(_QWORD *)this = &wmi::RefBase::`vftable';
  *((_DWORD *)this + 2) = 0;
  v10 = (SubscriptionConfigSnapshot *)((char *)this + 16);
  SubscriptionWriteData::SubscriptionWriteData((SubscriptionConfigSnapshot *)((char *)this + 16), a4, 1, a6);
  *(_QWORD *)this = &SubscriptionConfigSnapshot::`vftable';
  v54 = 0;
  v77 = 7;
  v76 = 0;
  LOWORD(v75[0]) = 0;
  v53 = 0;
  v56 = 0;
  _EventSources::_EventSources((_EventSources *)v74);
  v55 = EcConfigurationModeCustom;
  ConfigBase::GetRegEnumValue(
    (ConfigBase *)a2,
    L"ConfigurationMode",
    (struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueConfigurationMode,
    (unsigned int *)&v55);
  SubscriptionConfigModeReader::SubscriptionConfigModeReader((SubscriptionConfigModeReader *)v59, v55);
  Enabled = SubscriptionConfigReader::GetEnabled((SubscriptionConfigReader *)a2, &v54);
  v12 = *(struct tag_EcRpcMetadataPropertyList **)v10;
  *(_BYTE *)(*((_QWORD *)v12 + 1) + 8LL) = !Enabled || v54;
  **((_DWORD **)v12 + 1) = 1;
  if ( a3 && *a3 )
  {
    v13 = a7;
    SubscriptionConfigReader::GetEventSource((SubscriptionConfigReader *)a2, a3, (struct _EventSources *)v74, a7);
  }
  else
  {
    v13 = a7;
    SubscriptionConfigReader::GetEventSources((SubscriptionConfigReader *)a2, (struct _EventSources *)v74, a7);
  }
  SubscriptionWriteData::SetEventSources(v10, (const struct _EventSources *)v74);
  if ( (unsigned __int8)RegReadStringValue(a2[2], L"Description", v75) )
  {
    v14 = (const unsigned __int16 *)v75;
    if ( v77 >= 8 )
      v14 = v75[0];
    InitializeMetadataProp(*(struct tag_EcRpcMetadataPropertyList **)v10, 6u, v14);
  }
  if ( (unsigned __int8)RegReadStringValue(a2[2], L"URI", v75) )
  {
    v15 = (const unsigned __int16 *)v75;
    if ( v77 >= 8 )
      v15 = v75[0];
    InitializeMetadataProp(*(struct tag_EcRpcMetadataPropertyList **)v10, 7u, v15);
  }
  v55 = EcConfigurationModeCustom;
  ConfigBase::GetRegEnumValue(
    (ConfigBase *)a2,
    L"ConfigurationMode",
    (struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueConfigurationMode,
    (unsigned int *)&v55);
  v16 = *(struct tag_EcRpcMetadataPropertyList **)v10;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 200LL) = v55;
  *(_DWORD *)(*((_QWORD *)v16 + 1) + 192LL) = 2;
  if ( SubscriptionConfigReader::GetExpires((SubscriptionConfigReader *)a2, &v56) )
  {
    v17 = *(struct tag_EcRpcMetadataPropertyList **)v10;
    *(struct _FILETIME *)(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 224LL) = v56;
    *(_DWORD *)(*((_QWORD *)v17 + 1) + 216LL) = 3;
  }
  if ( (unsigned __int8)RegReadStringValue(a2[2], L"Dialect", v75) )
  {
    v18 = (const unsigned __int16 *)v75;
    if ( v77 >= 8 )
      v18 = v75[0];
    InitializeMetadataProp(*(struct tag_EcRpcMetadataPropertyList **)v10, 0x1Au, v18);
  }
  if ( (unsigned __int8)RegReadStringValue(a2[2], L"Query", v75) )
  {
    v19 = (const unsigned __int16 *)v75;
    if ( v77 >= 8 )
      v19 = v75[0];
    InitializeMetadataProp(*(struct tag_EcRpcMetadataPropertyList **)v10, 0xAu, v19);
  }
  if ( (unsigned __int8)RegReadStringValue(a2[2], L"TransportName", v75) )
  {
    v20 = (const unsigned __int16 *)v75;
    if ( v77 >= 8 )
      v20 = v75[0];
    InitializeMetadataProp(*(struct tag_EcRpcMetadataPropertyList **)v10, 0xBu, v20);
  }
  if ( RegReadDWORDValue(a2[2], L"TransportPort", (unsigned int *)&v53) && v53 )
  {
    v21 = *(struct tag_EcRpcMetadataPropertyList **)v10;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 296LL) = v53;
    *(_DWORD *)(*((_QWORD *)v21 + 1) + 288LL) = 2;
  }
  if ( v61 == 1
    && ConfigBase::GetRegEnumValue(
         (ConfigBase *)a2,
         L"DeliveryMode",
         (struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueDeliveryMode,
         (unsigned int *)&v53)
    || ConfigBase::GetRegEnumValue(
         (ConfigBase *)v59,
         L"DeliveryMode",
         (struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueDeliveryMode,
         (unsigned int *)&v53) )
  {
    v55 = EcConfigurationModeNormal;
    if ( !ConfigBase::GetRegEnumValue(
            (ConfigBase *)a2,
            L"SubscriptionType",
            (struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueSubscriptionType,
            (unsigned int *)&v55)
      || (v22 = EcDeliveryModePush, v55) )
    {
      v22 = v53;
    }
    SubscriptionWriteData::SetDeliveryMode(v10, v22);
  }
  if ( RegReadDWORDValue(a2[2], L"MaxItems", (unsigned int *)&v53) )
  {
    v23 = *(struct tag_EcRpcMetadataPropertyList **)v10;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 344LL) = v53;
    *(_DWORD *)(*((_QWORD *)v23 + 1) + 336LL) = 2;
  }
  if ( v61 == 1 && RegReadDWORDValue(a2[2], L"MaxLatencyTime", (unsigned int *)&v53)
    || RegReadDWORDValue(v60, L"MaxLatencyTime", (unsigned int *)&v53) )
  {
    v24 = *(struct tag_EcRpcMetadataPropertyList **)v10;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 368LL) = v53;
    *(_DWORD *)(*((_QWORD *)v24 + 1) + 360LL) = 2;
  }
  if ( v61 == 1 && RegReadDWORDValue(a2[2], L"HeartBeatInterval", (unsigned int *)&v53)
    || RegReadDWORDValue(v60, L"HeartBeatInterval", (unsigned int *)&v53) )
  {
    v25 = *(struct tag_EcRpcMetadataPropertyList **)v10;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 392LL) = v53;
    *(_DWORD *)(*((_QWORD *)v25 + 1) + 384LL) = 2;
  }
  RegEnumValue = ConfigBase::GetRegEnumValue(
                   (ConfigBase *)a2,
                   L"ContentFormat",
                   (struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueContentFormat,
                   (unsigned int *)&v53);
  v27 = v53;
  if ( !RegEnumValue )
    v27 = EcContentFormatRenderedText;
  SubscriptionWriteData::SetContentFormat(v10, v27);
  v28 = v75;
  if ( v77 >= 8 )
    v28 = (unsigned __int16 **)v75[0];
  v76 = 0;
  *(_WORD *)v28 = 0;
  RegReadStringValue(a2[2], L"Locale", v75);
  if ( !v76 )
  {
    ThreadLocale = GetThreadLocale();
    if ( !LCIDToLocaleName(ThreadLocale, Name, 85, 0) )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, LastError);
      }
      v63 = 0;
      v64 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v65 = 0;
      v66 = 0;
      v67 = LastError;
      v68 = -1;
      v69 = 456;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    std::wstring::assign(v75, Name);
  }
  v31 = (const unsigned __int16 *)v75;
  if ( v77 >= 8 )
    v31 = v75[0];
  InitializeMetadataProp(*(struct tag_EcRpcMetadataPropertyList **)v10, 0x11u, v31);
  v32 = v75;
  if ( v77 >= 8 )
    v32 = (unsigned __int16 **)v75[0];
  v76 = 0;
  *(_WORD *)v32 = 0;
  RegReadStringValue(a2[2], L"LogFile", v75);
  if ( !v76 )
    std::wstring::assign(v75, L"ForwardedEvents");
  v33 = (const unsigned __int16 *)v75;
  if ( v77 >= 8 )
    v33 = v75[0];
  InitializeMetadataProp(*(struct tag_EcRpcMetadataPropertyList **)v10, 0x13u, v33);
  if ( (unsigned __int8)RegReadStringValue(a2[2], L"PublisherName", v75) )
  {
    v34 = (const unsigned __int16 *)v75;
    if ( v77 >= 8 )
      v34 = v75[0];
    InitializeMetadataProp(*(struct tag_EcRpcMetadataPropertyList **)v10, 0x14u, v34);
  }
  if ( ConfigBase::GetRegEnumValue(
         (ConfigBase *)a2,
         L"CredentialsType",
         (struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueCredentialsType,
         (unsigned int *)&v53) )
  {
    v35 = *(struct tag_EcRpcMetadataPropertyList **)v10;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 512LL) = v53;
    v36 = *((_QWORD *)v35 + 1);
  }
  else
  {
    v37 = *(struct tag_EcRpcMetadataPropertyList **)v10;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 512LL) = 0;
    v36 = *((_QWORD *)v37 + 1);
  }
  *(_DWORD *)(v36 + 504) = 2;
  if ( (unsigned __int8)RegReadStringValue(a2[2], L"CommonUserName", v75) )
  {
    v39 = (const unsigned __int16 *)v75;
    if ( v77 >= 8 )
      v39 = v75[0];
    InitializeMetadataProp(*(struct tag_EcRpcMetadataPropertyList **)v10, 0x16u, v39);
  }
  *(_OWORD *)v57 = 0;
  v58 = 0;
  v70[0] = 0;
  v71 = ZeroPasswordString;
  v72 = v57;
  if ( v13 && SubscriptionConfigReader::ReadPassword(v38, (__int64)a2[2], (__int64)L"CommonPassword", v57) )
    InitializeMetadataProp(*(struct tag_EcRpcMetadataPropertyList **)v10, 0x17u, v57[0]);
  if ( (unsigned __int8)RegReadStringValue(a2[2], L"HostName", v75) )
  {
    v40 = (const unsigned __int16 *)v75;
    if ( v77 >= 8 )
      v40 = v75[0];
    InitializeMetadataProp(*(struct tag_EcRpcMetadataPropertyList **)v10, 0x18u, v40);
  }
  v55 = EcConfigurationModeNormal;
  if ( RegReadDWORDValue(a2[2], L"ReadExistingEvents", (unsigned int *)&v55) )
  {
    v41 = *(struct tag_EcRpcMetadataPropertyList **)v10;
    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 608LL) = v55 != EcConfigurationModeNormal;
    v42 = *((_QWORD *)v41 + 1);
  }
  else
  {
    v43 = *(struct tag_EcRpcMetadataPropertyList **)v10;
    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 608LL) = 0;
    v42 = *((_QWORD *)v43 + 1);
  }
  *(_DWORD *)(v42 + 600) = 1;
  if ( ConfigBase::GetRegEnumValue(
         (ConfigBase *)a2,
         L"SubscriptionType",
         (struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueSubscriptionType,
         (unsigned int *)&v53) )
  {
    v44 = *(struct tag_EcRpcMetadataPropertyList **)v10;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 656LL) = v53;
    v45 = *((_QWORD *)v44 + 1);
  }
  else
  {
    v46 = *(struct tag_EcRpcMetadataPropertyList **)v10;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 656LL) = 1;
    v45 = *((_QWORD *)v46 + 1);
  }
  *(_DWORD *)(v45 + 648) = 2;
  if ( (unsigned __int8)RegReadStringValue(a2[2], L"AllowedIssuerCAs", v75) )
  {
    v47 = (const unsigned __int16 *)v75;
    if ( v77 >= 8 )
      v47 = v75[0];
    InitializeMetadataProp(*(struct tag_EcRpcMetadataPropertyList **)v10, 0x1Cu, v47);
  }
  if ( (unsigned __int8)RegReadStringValue(a2[2], L"AllowedSubjects", v75) )
  {
    v48 = (const unsigned __int16 *)v75;
    if ( v77 >= 8 )
      v48 = v75[0];
    InitializeMetadataProp(*(struct tag_EcRpcMetadataPropertyList **)v10, 0x1Du, v48);
  }
  if ( (unsigned __int8)RegReadStringValue(a2[2], L"DeniedSubjects", v75) )
  {
    v49 = (const unsigned __int16 *)v75;
    if ( v77 >= 8 )
      v49 = v75[0];
    InitializeMetadataProp(*(struct tag_EcRpcMetadataPropertyList **)v10, 0x1Eu, v49);
  }
  if ( (unsigned __int8)RegReadStringValue(a2[2], L"AllowedSourceDomainComputers", v75) )
  {
    v50 = (const unsigned __int16 *)v75;
    if ( v77 >= 8 )
      v50 = v75[0];
    InitializeMetadataProp(*(struct tag_EcRpcMetadataPropertyList **)v10, 0x1Fu, v50);
  }
  wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v70);
  std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(v57);
  ConfigBase::~ConfigBase((ConfigBase *)v59);
  _EventSources::~_EventSources((_EventSources *)v74);
  LOBYTE(v51) = 1;
  std::wstring::_Tidy(v75, v51, 0);
  return this;
}

```

## disassembly

```asm
0x18001483c  push    rbp
0x18001483e  push    rbx
0x18001483f  push    rsi
0x180014840  push    rdi
0x180014841  push    r12
0x180014843  push    r13
0x180014845  push    r14
0x180014847  push    r15
0x180014849  lea     rbp, [rsp-138h]
0x180014851  sub     rsp, 238h
0x180014858  mov     rax, cs:__security_cookie
0x18001485f  xor     rax, rsp
0x180014862  mov     [rbp+170h+var_50], rax
0x180014869  mov     rax, r9
0x18001486c  mov     rsi, r8
0x18001486f  mov     rdi, rdx
0x180014872  mov     r15, rcx
0x180014875  mov     [rbp+170h+var_1B0], rcx
0x180014879  lea     rcx, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x180014880  mov     [r15], rcx
0x180014883  xor     r12d, r12d
0x180014886  mov     [r15+8], r12d
0x18001488a  lea     rbx, [r15+10h]
0x18001488e  mov     r9b, [rbp+170h+arg_28]; bool
0x180014895  lea     r13d, [r12+1]
0x18001489a  mov     r8b, r13b; bool
0x18001489d  mov     rdx, rax; struct tag_EcRpcMetadataPropertyList *
0x1800148a0  mov     rcx, rbx; this
0x1800148a3  call    ??0SubscriptionWriteData@@QEAA@AEAUtag_EcRpcMetadataPropertyList@@_N1@Z; SubscriptionWriteData::SubscriptionWriteData(tag_EcRpcMetadataPropertyList &,bool,bool)
0x1800148a8  nop
0x1800148a9  lea     rax, ??_7SubscriptionConfigSnapshot@@6B@; const SubscriptionConfigSnapshot::`vftable'
0x1800148b0  mov     [r15], rax
0x1800148b3  mov     [rsp+270h+var_24C], r12b
0x1800148b8  mov     [rbp+170h+var_108], 7
0x1800148c0  mov     [rbp+170h+var_110], r12
0x1800148c4  mov     word ptr [rbp+170h+var_120], r12w
0x1800148c9  mov     [rsp+270h+var_250], r12d
0x1800148ce  mov     qword ptr [rsp+270h+var_240.dwLowDateTime], r12
0x1800148d3  lea     rcx, [rbp+170h+var_1A0]; this
0x1800148d7  call    ??0_EventSources@@QEAA@XZ; _EventSources::_EventSources(void)
0x1800148dc  nop
0x1800148dd  mov     [rsp+270h+var_248], r13d
0x1800148e2  lea     r9, [rsp+270h+var_248]; unsigned int *
0x1800148e7  lea     r8, ?EnumNameValueConfigurationMode@@3PAU_ENUM_NAMEVALUE_PAIR@@A; struct _ENUM_NAMEVALUE_PAIR *
0x1800148ee  lea     rdx, aConfigurationm; "ConfigurationMode"
0x1800148f5  mov     rcx, rdi; this
0x1800148f8  call    ?GetRegEnumValue@ConfigBase@@IEBA_NPEBGPEAU_ENUM_NAMEVALUE_PAIR@@AEAK@Z; ConfigBase::GetRegEnumValue(ushort const *,_ENUM_NAMEVALUE_PAIR *,ulong &)
0x1800148fd  mov     edx, [rsp+270h+var_248]; enum _EC_SUBSCRIPTION_CONFIGURATION_MODE
0x180014901  lea     rcx, [rsp+270h+var_220]; this
0x180014906  call    ??0SubscriptionConfigModeReader@@QEAA@W4_EC_SUBSCRIPTION_CONFIGURATION_MODE@@@Z; SubscriptionConfigModeReader::SubscriptionConfigModeReader(_EC_SUBSCRIPTION_CONFIGURATION_MODE)
0x18001490b  nop
0x18001490c  lea     rdx, [rsp+270h+var_24C]; bool *
0x180014911  mov     rcx, rdi; this
0x180014914  call    ?GetEnabled@SubscriptionConfigReader@@QEBA_NAEA_N@Z; SubscriptionConfigReader::GetEnabled(bool &)
0x180014919  mov     rdx, [rbx]
0x18001491c  test    al, al
0x18001491e  jz      short loc_18001492D
0x180014920  mov     rcx, [rdx+8]
0x180014924  mov     al, [rsp+270h+var_24C]
0x180014928  mov     [rcx+8], al
0x18001492b  jmp     short loc_180014935
0x18001492d  mov     rax, [rdx+8]
0x180014931  mov     [rax+8], r13b
0x180014935  mov     rax, [rdx+8]
0x180014939  mov     [rax], r13d
0x18001493c  test    rsi, rsi
0x18001493f  jz      short loc_180014962
0x180014941  cmp     [rsi], r12w
0x180014945  jz      short loc_180014962
0x180014947  mov     r14b, [rbp+170h+arg_30]
0x18001494e  mov     r9b, r14b; bool
0x180014951  lea     r8, [rbp+170h+var_1A0]; struct _EventSources *
0x180014955  mov     rdx, rsi; unsigned __int16 *
0x180014958  mov     rcx, rdi; this
0x18001495b  call    ?GetEventSource@SubscriptionConfigReader@@QEBA_NPEBGAEAU_EventSources@@_N@Z; SubscriptionConfigReader::GetEventSource(ushort const *,_EventSources &,bool)
0x180014960  jmp     short loc_180014978
0x180014962  mov     r14b, [rbp+170h+arg_30]
0x180014969  mov     r8b, r14b; bool
0x18001496c  lea     rdx, [rbp+170h+var_1A0]; struct _EventSources *
0x180014970  mov     rcx, rdi; this
0x180014973  call    ?GetEventSources@SubscriptionConfigReader@@QEBA_NAEAU_EventSources@@_N@Z; SubscriptionConfigReader::GetEventSources(_EventSources &,bool)
0x180014978  lea     rdx, [rbp+170h+var_1A0]; struct _EventSources *
0x18001497c  mov     rcx, rbx; this
0x18001497f  call    ?SetEventSources@SubscriptionWriteData@@QEAAXAEBU_EventSources@@@Z; SubscriptionWriteData::SetEventSources(_EventSources const &)
0x180014984  lea     r8, [rbp+170h+var_120]
0x180014988  lea     rdx, aDescription; "Description"
0x18001498f  mov     rcx, [rdi+10h]
0x180014993  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x180014998  mov     esi, 8
0x18001499d  test    al, al
0x18001499f  jz      short loc_1800149B9
0x1800149a1  lea     r8, [rbp+170h+var_120]
0x1800149a5  cmp     [rbp+170h+var_108], rsi
0x1800149a9  cmovnb  r8, [rbp+170h+var_120]; unsigned __int16 *
0x1800149ae  lea     edx, [rsi-2]; unsigned int
0x1800149b1  mov     rcx, [rbx]; struct tag_EcRpcMetadataPropertyList *
0x1800149b4  call    ?InitializeMetadataProp@@YAXAEAUtag_EcRpcMetadataPropertyList@@KPEBG@Z; InitializeMetadataProp(tag_EcRpcMetadataPropertyList &,ulong,ushort const *)
0x1800149b9  lea     r8, [rbp+170h+var_120]
0x1800149bd  lea     rdx, aUri; "URI"
0x1800149c4  mov     rcx, [rdi+10h]
0x1800149c8  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x1800149cd  test    al, al
0x1800149cf  jz      short loc_1800149EB
0x1800149d1  lea     r8, [rbp+170h+var_120]
0x1800149d5  cmp     [rbp+170h+var_108], rsi
0x1800149d9  cmovnb  r8, [rbp+170h+var_120]; unsigned __int16 *
0x1800149de  mov     edx, 7; unsigned int
0x1800149e3  mov     rcx, [rbx]; struct tag_EcRpcMetadataPropertyList *
0x1800149e6  call    ?InitializeMetadataProp@@YAXAEAUtag_EcRpcMetadataPropertyList@@KPEBG@Z; InitializeMetadataProp(tag_EcRpcMetadataPropertyList &,ulong,ushort const *)
0x1800149eb  mov     [rsp+270h+var_248], r13d
0x1800149f0  lea     r9, [rsp+270h+var_248]; unsigned int *
0x1800149f5  lea     r8, ?EnumNameValueConfigurationMode@@3PAU_ENUM_NAMEVALUE_PAIR@@A; struct _ENUM_NAMEVALUE_PAIR *
0x1800149fc  lea     rdx, aConfigurationm; "ConfigurationMode"
0x180014a03  mov     rcx, rdi; this
0x180014a06  call    ?GetRegEnumValue@ConfigBase@@IEBA_NPEBGPEAU_ENUM_NAMEVALUE_PAIR@@AEAK@Z; ConfigBase::GetRegEnumValue(ushort const *,_ENUM_NAMEVALUE_PAIR *,ulong &)
0x180014a0b  mov     rdx, [rbx]
0x180014a0e  mov     rcx, [rdx+8]
0x180014a12  mov     eax, [rsp+270h+var_248]
0x180014a16  mov     [rcx+0C8h], eax
0x180014a1c  mov     rax, [rdx+8]
0x180014a20  mov     r13d, 2
0x180014a26  mov     [rax+0C0h], r13d
0x180014a2d  lea     rdx, [rsp+270h+var_240]; struct _FILETIME *
0x180014a32  mov     rcx, rdi; this
0x180014a35  call    ?GetExpires@SubscriptionConfigReader@@QEBA_NAEAU_FILETIME@@@Z; SubscriptionConfigReader::GetExpires(_FILETIME &)
0x180014a3a  test    al, al
0x180014a3c  jz      short loc_180014A5F
0x180014a3e  mov     rdx, [rbx]
0x180014a41  mov     rcx, [rdx+8]
0x180014a45  mov     rax, qword ptr [rsp+270h+var_240.dwLowDateTime]
0x180014a4a  mov     [rcx+0E0h], rax
0x180014a51  mov     rax, [rdx+8]
0x180014a55  mov     dword ptr [rax+0D8h], 3
0x180014a5f  lea     r8, [rbp+170h+var_120]
0x180014a63  lea     rdx, aDialect; "Dialect"
0x180014a6a  mov     rcx, [rdi+10h]
0x180014a6e  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x180014a73  test    al, al
0x180014a75  jz      short loc_180014A91
0x180014a77  lea     r8, [rbp+170h+var_120]
0x180014a7b  cmp     [rbp+170h+var_108], rsi
0x180014a7f  cmovnb  r8, [rbp+170h+var_120]; unsigned __int16 *
0x180014a84  mov     edx, 1Ah; unsigned int
0x180014a89  mov     rcx, [rbx]; struct tag_EcRpcMetadataPropertyList *
0x180014a8c  call    ?InitializeMetadataProp@@YAXAEAUtag_EcRpcMetadataPropertyList@@KPEBG@Z; InitializeMetadataProp(tag_EcRpcMetadataPropertyList &,ulong,ushort const *)
0x180014a91  lea     r8, [rbp+170h+var_120]
0x180014a95  lea     rdx, aQuery_0; "Query"
0x180014a9c  mov     rcx, [rdi+10h]
0x180014aa0  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x180014aa5  test    al, al
0x180014aa7  jz      short loc_180014AC3
0x180014aa9  lea     r8, [rbp+170h+var_120]
0x180014aad  cmp     [rbp+170h+var_108], rsi
0x180014ab1  cmovnb  r8, [rbp+170h+var_120]; unsigned __int16 *
0x180014ab6  mov     edx, 0Ah; unsigned int
0x180014abb  mov     rcx, [rbx]; struct tag_EcRpcMetadataPropertyList *
0x180014abe  call    ?InitializeMetadataProp@@YAXAEAUtag_EcRpcMetadataPropertyList@@KPEBG@Z; InitializeMetadataProp(tag_EcRpcMetadataPropertyList &,ulong,ushort const *)
0x180014ac3  lea     r8, [rbp+170h+var_120]
0x180014ac7  lea     rdx, aTransportname; "TransportName"
0x180014ace  mov     rcx, [rdi+10h]
0x180014ad2  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x180014ad7  test    al, al
0x180014ad9  jz      short loc_180014AF5
0x180014adb  lea     r8, [rbp+170h+var_120]
0x180014adf  cmp     [rbp+170h+var_108], rsi
0x180014ae3  cmovnb  r8, [rbp+170h+var_120]; unsigned __int16 *
0x180014ae8  mov     edx, 0Bh; unsigned int
0x180014aed  mov     rcx, [rbx]; struct tag_EcRpcMetadataPropertyList *
0x180014af0  call    ?InitializeMetadataProp@@YAXAEAUtag_EcRpcMetadataPropertyList@@KPEBG@Z; InitializeMetadataProp(tag_EcRpcMetadataPropertyList &,ulong,ushort const *)
0x180014af5  lea     r8, [rsp+270h+var_250]; unsigned int *
0x180014afa  lea     rdx, aTransportport; "TransportPort"
0x180014b01  mov     rcx, [rdi+10h]; HKEY
0x180014b05  call    ?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z; RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)
0x180014b0a  test    al, al
0x180014b0c  jz      short loc_180014B2E
0x180014b0e  mov     edx, [rsp+270h+var_250]
0x180014b12  test    edx, edx
0x180014b14  jz      short loc_180014B2E
0x180014b16  mov     rcx, [rbx]
0x180014b19  mov     rax, [rcx+8]
0x180014b1d  mov     [rax+128h], edx
0x180014b23  mov     rax, [rcx+8]
0x180014b27  mov     [rax+120h], r13d
0x180014b2e  cmp     [rsp+270h+var_208], 1
0x180014b33  jnz     short loc_180014B54
0x180014b35  lea     r9, [rsp+270h+var_250]; unsigned int *
0x180014b3a  lea     r8, ?EnumNameValueDeliveryMode@@3PAU_ENUM_NAMEVALUE_PAIR@@A; struct _ENUM_NAMEVALUE_PAIR *
0x180014b41  lea     rdx, aDeliverymode; "DeliveryMode"
0x180014b48  mov     rcx, rdi; this
0x180014b4b  call    ?GetRegEnumValue@ConfigBase@@IEBA_NPEBGPEAU_ENUM_NAMEVALUE_PAIR@@AEAK@Z; ConfigBase::GetRegEnumValue(ushort const *,_ENUM_NAMEVALUE_PAIR *,ulong &)
0x180014b50  test    al, al
0x180014b52  jnz     short loc_180014B75
0x180014b54  lea     r9, [rsp+270h+var_250]; unsigned int *
0x180014b59  lea     r8, ?EnumNameValueDeliveryMode@@3PAU_ENUM_NAMEVALUE_PAIR@@A; struct _ENUM_NAMEVALUE_PAIR *
0x180014b60  lea     rdx, aDeliverymode; "DeliveryMode"
0x180014b67  lea     rcx, [rsp+270h+var_220]; this
0x180014b6c  call    ?GetRegEnumValue@ConfigBase@@IEBA_NPEBGPEAU_ENUM_NAMEVALUE_PAIR@@AEAK@Z; ConfigBase::GetRegEnumValue(ushort const *,_ENUM_NAMEVALUE_PAIR *,ulong &)
0x180014b71  test    al, al
0x180014b73  jz      short loc_180014BAF
0x180014b75  mov     [rsp+270h+var_248], r12d
0x180014b7a  lea     r9, [rsp+270h+var_248]; unsigned int *
0x180014b7f  lea     r8, ?EnumNameValueSubscriptionType@@3PAU_ENUM_NAMEVALUE_PAIR@@A; struct _ENUM_NAMEVALUE_PAIR *
0x180014b86  lea     rdx, aSubscriptionty; "SubscriptionType"
0x180014b8d  mov     rcx, rdi; this
0x180014b90  call    ?GetRegEnumValue@ConfigBase@@IEBA_NPEBGPEAU_ENUM_NAMEVALUE_PAIR@@AEAK@Z; ConfigBase::GetRegEnumValue(ushort const *,_ENUM_NAMEVALUE_PAIR *,ulong &)
0x180014b95  test    al, al
0x180014b97  jz      short loc_180014BA3
0x180014b99  cmp     [rsp+270h+var_248], r12d
0x180014b9e  mov     edx, r13d
0x180014ba1  jz      short loc_180014BA7
0x180014ba3  mov     edx, [rsp+270h+var_250]; enum _EC_SUBSCRIPTION_DELIVERY_MODE
0x180014ba7  mov     rcx, rbx; this
0x180014baa  call    ?SetDeliveryMode@SubscriptionWriteData@@QEAAXW4_EC_SUBSCRIPTION_DELIVERY_MODE@@@Z; SubscriptionWriteData::SetDeliveryMode(_EC_SUBSCRIPTION_DELIVERY_MODE)
0x180014baf  lea     r8, [rsp+270h+var_250]; unsigned int *
0x180014bb4  lea     rdx, aMaxitems; "MaxItems"
0x180014bbb  mov     rcx, [rdi+10h]; HKEY
0x180014bbf  call    ?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z; RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)
0x180014bc4  test    al, al
0x180014bc6  jz      short loc_180014BE4
0x180014bc8  mov     rdx, [rbx]
0x180014bcb  mov     rcx, [rdx+8]
0x180014bcf  mov     eax, [rsp+270h+var_250]
0x180014bd3  mov     [rcx+158h], eax
0x180014bd9  mov     rax, [rdx+8]
0x180014bdd  mov     [rax+150h], r13d
0x180014be4  cmp     [rsp+270h+var_208], 1
0x180014be9  jnz     short loc_180014C04
0x180014beb  lea     r8, [rsp+270h+var_250]; unsigned int *
0x180014bf0  lea     rdx, aMaxlatencytime; "MaxLatencyTime"
0x180014bf7  mov     rcx, [rdi+10h]; HKEY
0x180014bfb  call    ?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z; RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)
0x180014c00  test    al, al
0x180014c02  jnz     short loc_180014C1E
0x180014c04  lea     r8, [rsp+270h+var_250]; unsigned int *
0x180014c09  lea     rdx, aMaxlatencytime; "MaxLatencyTime"
0x180014c10  mov     rcx, [rsp+270h+var_210]; HKEY
0x180014c15  call    ?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z; RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)
0x180014c1a  test    al, al
0x180014c1c  jz      short loc_180014C3A
0x180014c1e  mov     rdx, [rbx]
0x180014c21  mov     rcx, [rdx+8]
0x180014c25  mov     eax, [rsp+270h+var_250]
0x180014c29  mov     [rcx+170h], eax
0x180014c2f  mov     rax, [rdx+8]
0x180014c33  mov     [rax+168h], r13d
0x180014c3a  cmp     [rsp+270h+var_208], 1
0x180014c3f  jnz     short loc_180014C5A
0x180014c41  lea     r8, [rsp+270h+var_250]; unsigned int *
0x180014c46  lea     rdx, aHeartbeatinter; "HeartBeatInterval"
0x180014c4d  mov     rcx, [rdi+10h]; HKEY
0x180014c51  call    ?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z; RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)
0x180014c56  test    al, al
0x180014c58  jnz     short loc_180014C74
0x180014c5a  lea     r8, [rsp+270h+var_250]; unsigned int *
0x180014c5f  lea     rdx, aHeartbeatinter; "HeartBeatInterval"
0x180014c66  mov     rcx, [rsp+270h+var_210]; HKEY
0x180014c6b  call    ?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z; RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)
0x180014c70  test    al, al
0x180014c72  jz      short loc_180014C90
0x180014c74  mov     rdx, [rbx]
0x180014c77  mov     rcx, [rdx+8]
0x180014c7b  mov     eax, [rsp+270h+var_250]
0x180014c7f  mov     [rcx+188h], eax
0x180014c85  mov     rax, [rdx+8]
0x180014c89  mov     [rax+180h], r13d
0x180014c90  lea     r9, [rsp+270h+var_250]; unsigned int *
0x180014c95  lea     r8, ?EnumNameValueContentFormat@@3PAU_ENUM_NAMEVALUE_PAIR@@A; struct _ENUM_NAMEVALUE_PAIR *
0x180014c9c  lea     rdx, aContentformat; "ContentFormat"
0x180014ca3  mov     rcx, rdi; this
0x180014ca6  call    ?GetRegEnumValue@ConfigBase@@IEBA_NPEBGPEAU_ENUM_NAMEVALUE_PAIR@@AEAK@Z; ConfigBase::GetRegEnumValue(ushort const *,_ENUM_NAMEVALUE_PAIR *,ulong &)
0x180014cab  mov     rcx, rbx; this
0x180014cae  test    al, al
0x180014cb0  mov     edx, [rsp+270h+var_250]
0x180014cb4  jnz     short loc_180014CB9
0x180014cb6  mov     edx, r13d; enum _EC_SUBSCRIPTION_CONTENT_FORMAT
0x180014cb9  call    ?SetContentFormat@SubscriptionWriteData@@QEAAXW4_EC_SUBSCRIPTION_CONTENT_FORMAT@@@Z; SubscriptionWriteData::SetContentFormat(_EC_SUBSCRIPTION_CONTENT_FORMAT)
0x180014cbe  lea     rcx, [rbp+170h+var_120]
0x180014cc2  cmp     [rbp+170h+var_108], rsi
0x180014cc6  cmovnb  rcx, [rbp+170h+var_120]
0x180014ccb  mov     [rbp+170h+var_110], r12
0x180014ccf  mov     [rcx], r12w
0x180014cd3  lea     r8, [rbp+170h+var_120]
0x180014cd7  lea     rdx, aLocale; "Locale"
0x180014cde  mov     rcx, [rdi+10h]
0x180014ce2  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x180014ce7  cmp     [rbp+170h+var_110], r12
0x180014ceb  jnz     loc_180014DAF
0x180014cf1  call    cs:__imp_GetThreadLocale
0x180014cf7  xor     r9d, r9d; dwFlags
0x180014cfa  lea     r8d, [r9+55h]; cchName
0x180014cfe  lea     rdx, [rbp+170h+Name]; lpName
0x180014d02  mov     ecx, eax; Locale
0x180014d04  call    cs:__imp_LCIDToLocaleName
0x180014d0a  test    eax, eax
0x180014d0c  jnz     loc_180014DA2
0x180014d12  call    cs:__imp_GetLastError
0x180014d18  mov     ebx, eax
0x180014d1a  mov     eax, 507h
0x180014d1f  test    ebx, ebx
0x180014d21  cmovz   ebx, eax
  ... truncated ...
```
