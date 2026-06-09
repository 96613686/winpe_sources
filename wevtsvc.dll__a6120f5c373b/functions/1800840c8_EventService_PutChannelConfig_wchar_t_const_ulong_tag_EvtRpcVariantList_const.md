# EventService::PutChannelConfig(wchar_t const *,ulong,tag_EvtRpcVariantList const &)

- ea: `0x1800840c8`
- end: `0x180084c1c`
- name: `?PutChannelConfig@EventService@@QEAAXPEB_WKAEBUtag_EvtRpcVariantList@@@Z`
- size: `2900`
- prototype: `void __fastcall(PSRWLOCK SRWLock, const wchar_t *, int, const struct tag_EvtRpcVariantList *)`
- caller_count: `1`
- callee_count: `49`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1800a9420`

## callees

- `0x180013744`
- `0x180016250`
- `0x180017128`
- `0x180017b1c`
- `0x180017b60`
- `0x180028fb0`
- `0x180043a88`
- `0x180056fa4`
- `0x180057014`
- `0x18005714c`
- `0x1800572dc`
- `0x1800572f8`
- `0x180057310`
- `0x18005733c`
- `0x18005739c`
- `0x1800573b4`
- `0x180057440`
- `0x1800574a8`
- `0x1800574f0`
- `0x180057580`
- `0x180057870`
- `0x180057e30`
- `0x180058b2c`
- `0x180058b48`
- `0x180059440`
- `0x180059508`
- `0x18005a7e4`
- `0x18005af7c`
- `0x18005b6a0`
- `0x180071ff4`
- `0x1800840a0`
- `0x1800840c8`
- `0x180084c24`
- `0x180084c98`
- `0x180084f08`
- `0x180084f98`
- `0x1800896fc`
- `0x180092008`
- `0x18009342c`
- `0x18009aee0`
- `0x18009e81c`
- `0x1800a5a54`
- `0x1800a5b68`
- `0x1800a5c7c`
- `0x1800a5e04`
- `0x1800a5f18`
- `0x1800c15d4`
- `0x1800c168c`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180084a92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180084a92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084bb8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084bb8`
- `RPCRT4!RpcImpersonateClient` at `0x180084220`
- `RPCRT4!RpcImpersonateClient` at `0x180084220`
- `RPCRT4!RpcRevertToSelf` at `0x180084be7`
- `RPCRT4!RpcRevertToSelf` at `0x180084be7`

## string_xrefs

- `0x180084673`: `ChannelConfigException`
- `0x18008472f`: `ChannelConfigException`
- `0x1800847ef`: `ChannelConfigException`
- `0x1800848af`: `ChannelConfigException`
- `0x18008496f`: `ChannelConfigException`
- `0x180084a2f`: `ChannelConfigException`

## pseudocode

```c
void __fastcall EventService::PutChannelConfig(
        PSRWLOCK SRWLock,
        const wchar_t *a2,
        int a3,
        const struct tag_EvtRpcVariantList *a4)
{
  __int64 v8; // rdi
  unsigned int v9; // eax
  unsigned int v10; // esi
  unsigned int v11; // eax
  unsigned int v12; // esi
  void *v13; // rax
  __int64 v14; // rsi
  char ModifiedMetadataProp_3; // al
  char v16; // al
  char v17; // al
  char ModifiedMetadataProp_1; // al
  __int64 v19; // r8
  __int64 v20; // rcx
  char v21; // al
  char v22; // al
  char v23; // al
  char v24; // al
  char v25; // al
  char v26; // cl
  char v27; // al
  char v28; // dl
  char v29; // cl
  char v30; // al
  __int64 v31; // rdx
  char v32; // al
  __int64 CurrentChannelPolicy; // rdi
  unsigned __int64 v34; // r14
  char v35; // al
  __int64 v36; // rcx
  __int64 v37; // r12
  __int128 v38; // xmm6
  __int64 v39; // r13
  __int64 v40; // rbx
  bool v41[8]; // [rsp+38h] [rbp-D0h] BYREF
  struct _GUID v42; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v43; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v44[12]; // [rsp+68h] [rbp-A0h]
  __int64 v45; // [rsp+74h] [rbp-94h]
  char v46; // [rsp+7Ch] [rbp-8Ch]
  __int128 v47; // [rsp+80h] [rbp-88h] BYREF
  int v48; // [rsp+90h] [rbp-78h]
  int v49; // [rsp+94h] [rbp-74h]
  int v50; // [rsp+98h] [rbp-70h]
  int v51; // [rsp+9Ch] [rbp-6Ch]
  int v52; // [rsp+A0h] [rbp-68h]
  int v53[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v54; // [rsp+D0h] [rbp-38h]
  char v55; // [rsp+D9h] [rbp-2Fh]
  __int128 v56; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+F8h] [rbp-10h] BYREF
  unsigned int v58; // [rsp+110h] [rbp+8h]
  __int64 v59; // [rsp+114h] [rbp+Ch]
  char v60; // [rsp+11Ch] [rbp+14h]
  wchar_t *v61[5]; // [rsp+120h] [rbp+18h] BYREF
  int v62[14]; // [rsp+148h] [rbp+40h] BYREF
  bool v63; // [rsp+180h] [rbp+78h]
  __int64 v64; // [rsp+188h] [rbp+80h]
  struct _GUID v65; // [rsp+190h] [rbp+88h]
  unsigned int Data1; // [rsp+1B0h] [rbp+A8h]
  char v67; // [rsp+1BAh] [rbp+B2h]
  __int64 v68; // [rsp+220h] [rbp+118h]
  bool v69; // [rsp+228h] [rbp+120h]
  bool v70; // [rsp+229h] [rbp+121h]
  char v71; // [rsp+230h] [rbp+128h]
  char v72; // [rsp+231h] [rbp+129h]
  char v73; // [rsp+232h] [rbp+12Ah]
  char v74; // [rsp+234h] [rbp+12Ch]
  char v75; // [rsp+236h] [rbp+12Eh]
  char v76; // [rsp+237h] [rbp+12Fh]
  char v77; // [rsp+238h] [rbp+130h]
  char v78; // [rsp+23Ah] [rbp+132h]
  char v79; // [rsp+23Bh] [rbp+133h]
  char v80; // [rsp+23Ch] [rbp+134h]
  char v81; // [rsp+244h] [rbp+13Ch]
  __int64 v82; // [rsp+258h] [rbp+150h]
  __int64 v83; // [rsp+260h] [rbp+158h]
  __int64 v84; // [rsp+268h] [rbp+160h]
  _BYTE v85[256]; // [rsp+2B8h] [rbp+1B0h] BYREF

  EventService::WaitForInit(SRWLock);
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  *(_QWORD *)v53 = a2;
  v54 = v8;
  v9 = ScanForInvalidChars(v53, 15000);
  v10 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v9);
    }
    pExceptionObject[0] = &byte_1800EC961;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v58 = v10;
    v59 = -1;
    v60 = 0;
    throw (EvtException *)pExceptionObject;
  }
  if ( BYTE4(SRWLock[60].Ptr) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 50);
    }
    v43 = 0;
    *(_QWORD *)v44 = 0;
    *(_DWORD *)&v44[8] = 50;
    v45 = 0x93AFFFFFFFFLL;
    throw (EvtException *)&v43;
  }
  v11 = RpcImpersonateClient(0);
  v12 = v11;
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v11);
    }
    *(_QWORD *)&v43 = &byte_1800EC961;
    *((_QWORD *)&v43 + 1) = 0;
    *(_QWORD *)v44 = 0;
    *(_DWORD *)&v44[8] = v12;
    v45 = -1;
    v46 = 0;
    throw (EvtException *)&v43;
  }
  v55 = 1;
  *(_QWORD *)v53 = a2;
  v54 = v8;
  ChannelConfigWriter::ChannelConfigWriter((int)v62, (int)v53, a3, 0, HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL);
  v13 = operator new(0x90u);
  *(_QWORD *)v53 = v13;
  if ( v13 )
  {
    *(_QWORD *)&v42.Data1 = v83;
    *(_QWORD *)v42.Data4 = (v84 - v83) >> 1;
    v14 = ChannelConfigReader::ChannelConfigReader(v13, &v42, v82);
  }
  else
  {
    v14 = 0;
  }
  *(_QWORD *)v53 = v14;
  ModifiedMetadataProp_3 = ReadModifiedMetadataProp_3(a4, 4, v41);
  v74 = ModifiedMetadataProp_3 | v74 & 0xFE;
  v42.Data1 = ChannelConfigReader::GetIsolation((ChannelConfigReader *)v14);
  v16 = ReadModifiedMetadataProp(a4, 1, &v42);
  v62[13] = v42.Data1;
  v72 = v16 | v72 & 0xFE;
  v42.Data1 = *(_DWORD *)(v14 + 136);
  v17 = ReadModifiedMetadataProp(a4, 2, &v42);
  v62[12] = v42.Data1;
  v73 = v17 | v73 & 0xFE;
  ChannelConfigReader::GetChannelAccessSddl((ChannelConfigReader *)v14);
  ModifiedMetadataProp_1 = ReadModifiedMetadataProp_1(a4, 5, pExceptionObject);
  v20 = -1;
  do
    ++v20;
  while ( *(_WORD *)(pExceptionObject[0] + 2 * v20) );
  *(_QWORD *)&v42.Data1 = pExceptionObject[0];
  *(_QWORD *)v42.Data4 = v20;
  LOBYTE(v19) = ModifiedMetadataProp_1;
  ChannelConfigWriteData::SetChannelAccessSddl(v62, &v42, v19);
  v41[0] = ChannelConfigReader::GetRetention((ChannelConfigReader *)v14);
  v21 = ReadModifiedMetadataProp_3(a4, 6, v41);
  v69 = v41[0];
  v75 = v21 | v75 & 0xFE;
  v41[0] = ChannelConfigReader::GetAutoBackup((ChannelConfigReader *)v14);
  v22 = ReadModifiedMetadataProp_3(a4, 7, v41);
  v70 = v41[0];
  v76 = v22 | v76 & 0xFE;
  ChannelConfigReader::GetLogFilePath(v14, v61);
  v23 = ReadModifiedMetadataProp_1(a4, 9, v61);
  ChannelConfigWriteData::SetLogFilePath((ChannelConfigWriteData *)v62, v61[0], v23);
  *(_QWORD *)&v42.Data1 = ChannelConfigReader::GetMaxSize((ChannelConfigReader *)v14);
  v24 = ReadModifiedMetadataProp_2(a4, 8, &v42);
  v68 = *(_QWORD *)&v42.Data1;
  v77 = v24 | v77 & 0xFE;
  v42.Data1 = ChannelConfigReader::GetFileMax((ChannelConfigReader *)v14);
  v25 = ReadModifiedMetadataProp(a4, 20, &v42);
  v26 = v81;
  if ( v42.Data1 <= 1 )
    v26 = v81 | 3;
  Data1 = v42.Data1;
  v81 = v25 | v26 & 0xFE;
  v41[0] = ChannelConfigReader::GetRawEnabled((ChannelConfigReader *)v14);
  v27 = ReadModifiedMetadataProp_3(a4, 0, v41);
  v63 = v41[0];
  v71 = v27 | v71 & 0xFE;
  v42.Data1 = ChannelConfigReader::GetLevel((ChannelConfigReader *)v14);
  v28 = ReadModifiedMetadataProp(a4, 10, &v42);
  v29 = -1;
  if ( v42.Data1 <= 0xFF )
    v29 = v42.Data1;
  v67 = v29;
  v78 = v28 | v78 & 0xFE;
  *(_QWORD *)&v42.Data1 = ChannelConfigReader::GetKeywords((ChannelConfigReader *)v14);
  v30 = ReadModifiedMetadataProp_2(a4, 11, &v42);
  v64 = *(_QWORD *)&v42.Data1;
  v79 = v30 | v79 & 0xFE;
  ChannelConfigReader::GetControlGuid((ChannelConfigReader *)v14, &v42);
  v32 = ReadModifiedMetadataProp_0(a4, v31, &v42);
  v65 = v42;
  v80 = v32 | v80 & 0xFE;
  ChannelConfigReader::GetBufferSize((ChannelConfigReader *)v14);
  if ( (unsigned __int8)ReadModifiedMetadataProp(a4, 13, &v42) )
  {
    *(_QWORD *)&v43 = 0;
    *(_DWORD *)v44 = 15023;
    *(_QWORD *)&v44[4] = 0x570000000DLL;
    v45 = 0xFFFFFFFFLL;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        113,
        (unsigned int)&WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
        (unsigned int)"ChannelConfigException",
        87);
    }
    v47 = 0;
    v48 = 15023;
    v49 = 13;
    v50 = 87;
    v51 = -1;
    v52 = 0;
    *((_QWORD *)&v43 + 1) = 0;
    throw (ChannelConfigException *)&v47;
  }
  ChannelConfigReader::GetMinBuffers((ChannelConfigReader *)v14);
  if ( (unsigned __int8)ReadModifiedMetadataProp(a4, 14, &v42) )
  {
    *(_QWORD *)&v47 = 0;
    v48 = 15023;
    v49 = 14;
    v50 = 87;
    v51 = -1;
    v52 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        114,
        (unsigned int)&WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
        (unsigned int)"ChannelConfigException",
        87);
    }
    v43 = 0;
    *(_DWORD *)v44 = 15023;
    *(_QWORD *)&v44[4] = 0x570000000ELL;
    v45 = 0xFFFFFFFFLL;
    *((_QWORD *)&v47 + 1) = 0;
    throw (ChannelConfigException *)&v43;
  }
  ChannelConfigReader::GetMaxBuffers((ChannelConfigReader *)v14);
  if ( (unsigned __int8)ReadModifiedMetadataProp(a4, 15, &v42) )
  {
    *(_QWORD *)&v47 = 0;
    v48 = 15023;
    v49 = 15;
    v50 = 87;
    v51 = -1;
    v52 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        115,
        (unsigned int)&WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
        (unsigned int)"ChannelConfigException",
        87);
    }
    v43 = 0;
    *(_DWORD *)v44 = 15023;
    *(_QWORD *)&v44[4] = 0x570000000FLL;
    v45 = 0xFFFFFFFFLL;
    *((_QWORD *)&v47 + 1) = 0;
    throw (ChannelConfigException *)&v43;
  }
  ChannelConfigReader::GetLatency((ChannelConfigReader *)v14);
  if ( (unsigned __int8)ReadModifiedMetadataProp(a4, 16, &v42) )
  {
    *(_QWORD *)&v47 = 0;
    v48 = 15023;
    v49 = 16;
    v50 = 87;
    v51 = -1;
    v52 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        116,
        (unsigned int)&WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
        (unsigned int)"ChannelConfigException",
        87);
    }
    v43 = 0;
    *(_DWORD *)v44 = 15023;
    *(_QWORD *)&v44[4] = 0x5700000010LL;
    v45 = 0xFFFFFFFFLL;
    *((_QWORD *)&v47 + 1) = 0;
    throw (ChannelConfigException *)&v43;
  }
  ChannelConfigReader::GetClockType((ChannelConfigReader *)v14);
  if ( (unsigned __int8)ReadModifiedMetadataProp(a4, 17, &v42) )
  {
    *(_QWORD *)&v47 = 0;
    v48 = 15023;
    v49 = 17;
    v50 = 87;
    v51 = -1;
    v52 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        117,
        (unsigned int)&WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
        (unsigned int)"ChannelConfigException",
        87);
    }
    v43 = 0;
    *(_DWORD *)v44 = 15023;
    *(_QWORD *)&v44[4] = 0x5700000011LL;
    v45 = 0xFFFFFFFFLL;
    *((_QWORD *)&v47 + 1) = 0;
    throw (ChannelConfigException *)&v43;
  }
  ChannelConfigReader::GetSidType((ChannelConfigReader *)v14);
  if ( (unsigned __int8)ReadModifiedMetadataProp(a4, 18, &v42) )
  {
    *(_QWORD *)&v47 = 0;
    v48 = 15023;
    v49 = 18;
    v50 = 87;
    v51 = -1;
    v52 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        118,
        (unsigned int)&WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
        (unsigned int)"ChannelConfigException",
        87);
    }
    v43 = 0;
    *(_DWORD *)v44 = 15023;
    *(_QWORD *)&v44[4] = 0x5700000012LL;
    v45 = 0xFFFFFFFFLL;
    *((_QWORD *)&v47 + 1) = 0;
    throw (ChannelConfigException *)&v43;
  }
  ChannelConfigWriter::Validate((ChannelConfigWriter *)v62, 0);
  *(_QWORD *)&v42.Data1 = SRWLock;
  AcquireSRWLockExclusive(SRWLock);
  if ( (v72 & 3) != 0 || (v80 & 3) != 0 )
  {
    *(_QWORD *)&v56 = a2;
    *((_QWORD *)&v56 + 1) = v8;
    SessionConfig::DeleteChannel(&v56);
  }
  ChannelConfigWriter::Save((ChannelConfigWriter *)v62, 0);
  *(_QWORD *)&v56 = a2;
  *((_QWORD *)&v56 + 1) = v8;
  CurrentChannelPolicy = PolicyManager::GetCurrentChannelPolicy(SRWLock + 12, &v47);
  v34 = v14 + 64;
  v35 = *(_BYTE *)(v14 + 128);
  if ( *(_BYTE *)(CurrentChannelPolicy + 64) )
  {
    v36 = v14 + 64;
    if ( v35 )
    {
      v37 = *(_QWORD *)CurrentChannelPolicy;
      v38 = *(_OWORD *)(CurrentChannelPolicy + 8);
      v39 = *(_QWORD *)(CurrentChannelPolicy + 24);
      v40 = *(_QWORD *)(CurrentChannelPolicy + 16);
      *(_QWORD *)CurrentChannelPolicy = CurrentChannelPolicy;
      *(_QWORD *)(CurrentChannelPolicy + 8) = CurrentChannelPolicy;
      *(_QWORD *)(CurrentChannelPolicy + 16) = CurrentChannelPolicy;
      *(_QWORD *)(CurrentChannelPolicy + 24) = 0;
      utl::set<void *,utl::less<void *>,utl::allocator<void *>>::~set<void *,utl::less<void *>,utl::allocator<void *>>(v36);
      if ( v40 != CurrentChannelPolicy )
      {
        *(_QWORD *)(v37 & 0xFFFFFFFFFFFFFFFEuLL) = v34 | 1;
        *(_QWORD *)v34 = v37;
        *(_OWORD *)(v14 + 72) = v38;
        *(_QWORD *)(v14 + 88) = v39;
      }
      Buffer::operator=(v14 + 96, CurrentChannelPolicy + 32);
    }
    else
    {
      ChannelPolicy::ChannelPolicy(v36, CurrentChannelPolicy);
      *(_BYTE *)(v14 + 128) = 1;
    }
  }
  else if ( v35 )
  {
    ChannelPolicy::~ChannelPolicy((ChannelPolicy *)(v14 + 64));
    *(_BYTE *)(v14 + 128) = 0;
  }
  utl::_OptionalData1<ChannelPolicy,0>::~_OptionalData1<ChannelPolicy,0>(&v47);
  v56 = 0;
  ChannelConfigSnapshot::ChannelConfigSnapshot(v85, v14, &v56);
  SessionConfig::UpdateAutologgerForChannel((const struct ChannelConfigSnapshot *)v85, (void *)0xFFFFFFFFFFFFFFFFLL);
  ChannelConfigSnapshot::~ChannelConfigSnapshot((ChannelConfigSnapshot *)v85);
  ReleaseSRWLockExclusive(SRWLock);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v61);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(pExceptionObject);
  utl::unique_ptr<ChannelConfigReader,utl::default_delete<ChannelConfigReader>>::~unique_ptr<ChannelConfigReader,utl::default_delete<ChannelConfigReader>>(v53);
  ChannelConfigWriter::~ChannelConfigWriter((ChannelConfigWriter *)v62);
  RpcRevertToSelf();
}

```

## disassembly

```asm
0x1800840c8  mov     rax, rsp
0x1800840cb  mov     [rax+10h], rbx
0x1800840cf  push    rbp
0x1800840d0  push    rsi
0x1800840d1  push    rdi
0x1800840d2  push    r12
0x1800840d4  push    r13
0x1800840d6  push    r14
0x1800840d8  push    r15
0x1800840da  lea     rbp, [rax-308h]
0x1800840e1  sub     rsp, 3D0h
0x1800840e8  movaps  xmmword ptr [rax-48h], xmm6
0x1800840ec  mov     rax, cs:__security_cookie
0x1800840f3  xor     rax, rsp
0x1800840f6  mov     [rbp+300h+var_50], rax
0x1800840fd  mov     rbx, r9
0x180084100  mov     r12d, r8d
0x180084103  mov     r14, rdx
0x180084106  mov     r15, rcx
0x180084109  xor     r13d, r13d
0x18008410c  call    ?WaitForInit@EventService@@AEAAXXZ; EventService::WaitForInit(void)
0x180084111  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180084115  inc     rdi
0x180084118  cmp     [r14+rdi*2], r13w
0x18008411d  jnz     short loc_180084115
0x18008411f  mov     qword ptr [rbp+300h+var_340], r14
0x180084123  mov     [rbp+300h+var_338], rdi
0x180084127  mov     edx, 3A98h
0x18008412c  lea     rcx, [rbp+300h+var_340]
0x180084130  call    ScanForInvalidChars
0x180084135  mov     esi, eax
0x180084137  test    eax, eax
0x180084139  jz      short loc_1800841A7
0x18008413b  lea     rcx, WPP_GLOBAL_Control
0x180084142  mov     r10, cs:WPP_GLOBAL_Control
0x180084149  cmp     r10, rcx
0x18008414c  jz      short loc_180084174
0x18008414e  test    byte ptr [r10+1Ch], 8
0x180084153  jz      short loc_180084174
0x180084155  cmp     byte ptr [r10+19h], 2
0x18008415a  jb      short loc_180084174
0x18008415c  mov     edx, 6Eh ; 'n'
0x180084161  mov     r9d, eax
0x180084164  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x18008416b  mov     rcx, [r10+10h]
0x18008416f  call    WPP_SF_d
0x180084174  lea     rax, byte_1800EC961
0x18008417b  mov     [rbp+300h+pExceptionObject], rax
0x18008417f  mov     [rbp+300h+var_308], r13
0x180084183  mov     [rbp+300h+var_300], r13
0x180084187  mov     [rbp+300h+var_2F8], esi
0x18008418a  mov     [rbp+300h+var_2F4], 0FFFFFFFFFFFFFFFFh
0x180084192  mov     [rbp+300h+var_2EC], r13b
0x180084196  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18008419d  lea     rcx, [rbp+300h+pExceptionObject]; pExceptionObject
0x1800841a1  call    _CxxThrowException_0
0x1800841a7  cmp     [r15+1E4h], r13b
0x1800841ae  jz      short loc_18008421E
0x1800841b0  lea     rcx, WPP_GLOBAL_Control
0x1800841b7  mov     ebx, 32h ; '2'
0x1800841bc  mov     rax, cs:WPP_GLOBAL_Control
0x1800841c3  cmp     rax, rcx
0x1800841c6  jz      short loc_1800841EA
0x1800841c8  test    byte ptr [rax+1Ch], 8
0x1800841cc  jz      short loc_1800841EA
0x1800841ce  cmp     byte ptr [rax+19h], 2
0x1800841d2  jb      short loc_1800841EA
0x1800841d4  lea     edx, [rbx+3Dh]
0x1800841d7  mov     r9d, ebx
0x1800841da  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x1800841e1  mov     rcx, [rax+10h]
0x1800841e5  call    WPP_SF_d
0x1800841ea  xorps   xmm0, xmm0
0x1800841ed  movdqu  [rsp+400h+var_3B8+8], xmm0
0x1800841f3  mov     qword ptr [rsp+400h+var_3A0], r13
0x1800841f8  mov     dword ptr [rsp+400h+var_39C+4], ebx
0x1800841fc  mov     dword ptr [rsp+400h+var_394], 0FFFFFFFFh
0x180084204  mov     dword ptr [rsp+400h+var_390], 93Ah
0x18008420c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180084213  lea     rcx, [rsp+400h+var_3B8+8]; pExceptionObject
0x180084218  call    _CxxThrowException_0
0x18008421e  xor     ecx, ecx; BindingHandle
0x180084220  call    cs:__imp_RpcImpersonateClient
0x180084226  mov     esi, eax
0x180084228  test    eax, eax
0x18008422a  jz      short loc_18008429F
0x18008422c  lea     rcx, WPP_GLOBAL_Control
0x180084233  mov     r10, cs:WPP_GLOBAL_Control
0x18008423a  cmp     r10, rcx
0x18008423d  jz      short loc_180084265
0x18008423f  test    byte ptr [r10+1Ch], 8
0x180084244  jz      short loc_180084265
0x180084246  cmp     byte ptr [r10+19h], 2
0x18008424b  jb      short loc_180084265
0x18008424d  mov     edx, 70h ; 'p'
0x180084252  mov     r9d, eax
0x180084255  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x18008425c  mov     rcx, [r10+10h]
0x180084260  call    WPP_SF_d
0x180084265  lea     rax, byte_1800EC961
0x18008426c  mov     qword ptr [rsp+400h+var_3B8+8], rax
0x180084271  mov     [rsp+400h+var_3A8], r13
0x180084276  mov     qword ptr [rsp+400h+var_3A0], r13
0x18008427b  mov     dword ptr [rsp+400h+var_39C+4], esi
0x18008427f  mov     qword ptr [rsp+400h+var_394], 0FFFFFFFFFFFFFFFFh
0x180084288  mov     byte ptr [rsp+400h+var_390+4], r13b
0x18008428d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180084294  lea     rcx, [rsp+400h+var_3B8+8]; pExceptionObject
0x180084299  call    _CxxThrowException_0
0x18008429f  mov     [rbp+300h+var_32F], 1
0x1800842a3  mov     qword ptr [rbp+300h+var_340], r14
0x1800842a7  mov     [rbp+300h+var_338], rdi
0x1800842ab  mov     [rsp+400h+hKey], 0FFFFFFFFFFFFFFFFh; hKey
0x1800842b4  xor     r9d, r9d; int
0x1800842b7  mov     r8d, r12d; int
0x1800842ba  lea     rdx, [rbp+300h+var_340]; int
0x1800842be  lea     rcx, [rbp+300h+var_2C0]; int
0x1800842c2  call    ??0ChannelConfigWriter@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@K_NPEAX@Z; ChannelConfigWriter::ChannelConfigWriter(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,ulong,bool,void *)
0x1800842c7  nop
0x1800842c8  mov     ecx, 90h; dwBytes
0x1800842cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800842d2  mov     qword ptr [rbp+300h+var_340], rax
0x1800842d6  test    rax, rax
0x1800842d9  jz      short loc_180084312
0x1800842db  mov     rcx, [rbp+300h+var_1A8]
0x1800842e2  mov     qword ptr [rsp+400h+var_3C8.Data4], rcx
0x1800842e7  mov     rdx, [rbp+300h+var_1A0]
0x1800842ee  sub     rdx, rcx
0x1800842f1  sar     rdx, 1
0x1800842f4  mov     qword ptr [rsp+400h+var_3B8], rdx
0x1800842f9  mov     r8, [rbp+300h+var_1B0]
0x180084300  lea     rdx, [rsp+400h+var_3C8.Data4]
0x180084305  mov     rcx, rax
0x180084308  call    ??0ChannelConfigReader@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAX@Z; ChannelConfigReader::ChannelConfigReader(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,void *)
0x18008430d  mov     rsi, rax
0x180084310  jmp     short loc_180084315
0x180084312  mov     rsi, r13
0x180084315  mov     qword ptr [rbp+300h+var_340], rsi
0x180084319  lea     r8, [rsp+400h+var_3D0]
0x18008431e  mov     edx, 4
0x180084323  mov     rcx, rbx
0x180084326  call    ReadModifiedMetadataProp_3
0x18008432b  mov     cl, [rbp+300h+var_1D4]
0x180084331  mov     r12b, 0FEh
0x180084334  and     cl, r12b
0x180084337  or      cl, al
0x180084339  mov     [rbp+300h+var_1D4], cl
0x18008433f  mov     rcx, rsi; this
0x180084342  call    ?GetIsolation@ChannelConfigReader@@QEBA?AW4_EVT_CHANNEL_ISOLATION_TYPE@@XZ; ChannelConfigReader::GetIsolation(void)
0x180084347  mov     dword ptr [rsp+400h+var_3C8.Data4], eax
0x18008434b  lea     r8, [rsp+400h+var_3C8.Data4]
0x180084350  mov     edx, 1
0x180084355  mov     rcx, rbx
0x180084358  call    ReadModifiedMetadataProp
0x18008435d  mov     ecx, dword ptr [rsp+400h+var_3C8.Data4]
0x180084361  mov     [rbp+300h+var_28C], ecx
0x180084364  mov     cl, [rbp+300h+var_1D7]
0x18008436a  and     cl, r12b
0x18008436d  or      cl, al
0x18008436f  mov     [rbp+300h+var_1D7], cl
0x180084375  mov     eax, [rsi+88h]
0x18008437b  mov     dword ptr [rsp+400h+var_3C8.Data4], eax
0x18008437f  lea     r8, [rsp+400h+var_3C8.Data4]
0x180084384  mov     edx, 2
0x180084389  mov     rcx, rbx
0x18008438c  call    ReadModifiedMetadataProp
0x180084391  mov     ecx, dword ptr [rsp+400h+var_3C8.Data4]
0x180084395  mov     [rbp+300h+var_290], ecx
0x180084398  mov     cl, [rbp+300h+var_1D6]
0x18008439e  and     cl, r12b
0x1800843a1  or      cl, al
0x1800843a3  mov     [rbp+300h+var_1D6], cl
0x1800843a9  lea     rdx, [rbp+300h+pExceptionObject]
0x1800843ad  mov     rcx, rsi; this
0x1800843b0  call    ?GetChannelAccessSddl@ChannelConfigReader@@QEBA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@XZ; ChannelConfigReader::GetChannelAccessSddl(void)
0x1800843b5  nop
0x1800843b6  lea     r8, [rbp+300h+pExceptionObject]
0x1800843ba  mov     edx, 5
0x1800843bf  mov     rcx, rbx
0x1800843c2  call    ReadModifiedMetadataProp_1
0x1800843c7  mov     rdx, [rbp+300h+pExceptionObject]
0x1800843cb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800843cf  inc     rcx
0x1800843d2  cmp     [rdx+rcx*2], r13w
0x1800843d7  jnz     short loc_1800843CF
0x1800843d9  mov     qword ptr [rsp+400h+var_3C8.Data4], rdx
0x1800843de  mov     qword ptr [rsp+400h+var_3B8], rcx
0x1800843e3  mov     r8b, al
0x1800843e6  lea     rdx, [rsp+400h+var_3C8.Data4]
0x1800843eb  lea     rcx, [rbp+300h+var_2C0]
0x1800843ef  call    ?SetChannelAccessSddl@ChannelConfigWriteData@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@_N@Z; ChannelConfigWriteData::SetChannelAccessSddl(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool)
0x1800843f4  mov     rcx, rsi; this
0x1800843f7  call    ?GetRetention@ChannelConfigReader@@QEBA_NXZ; ChannelConfigReader::GetRetention(void)
0x1800843fc  mov     [rsp+400h+var_3D0], al
0x180084400  lea     r8, [rsp+400h+var_3D0]
0x180084405  mov     edx, 6
0x18008440a  mov     rcx, rbx
0x18008440d  call    ReadModifiedMetadataProp_3
0x180084412  mov     cl, [rsp+400h+var_3D0]
0x180084416  mov     [rbp+300h+var_1E0], cl
0x18008441c  mov     cl, [rbp+300h+var_1D2]
0x180084422  and     cl, r12b
0x180084425  or      cl, al
0x180084427  mov     [rbp+300h+var_1D2], cl
0x18008442d  mov     rcx, rsi; this
0x180084430  call    ?GetAutoBackup@ChannelConfigReader@@QEBA_NXZ; ChannelConfigReader::GetAutoBackup(void)
0x180084435  mov     [rsp+400h+var_3D0], al
0x180084439  lea     r8, [rsp+400h+var_3D0]
0x18008443e  mov     edx, 7
0x180084443  mov     rcx, rbx
0x180084446  call    ReadModifiedMetadataProp_3
0x18008444b  mov     cl, [rsp+400h+var_3D0]
0x18008444f  mov     [rbp+300h+var_1DF], cl
0x180084455  mov     cl, [rbp+300h+var_1D1]
0x18008445b  and     cl, r12b
0x18008445e  or      cl, al
0x180084460  mov     [rbp+300h+var_1D1], cl
0x180084466  lea     rdx, [rbp+300h+var_2E8]
0x18008446a  mov     rcx, rsi
0x18008446d  call    ?GetLogFilePath@ChannelConfigReader@@QEBA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@XZ; ChannelConfigReader::GetLogFilePath(void)
0x180084472  nop
0x180084473  lea     r8, [rbp+300h+var_2E8]
0x180084477  mov     edx, 9
0x18008447c  mov     rcx, rbx
0x18008447f  call    ReadModifiedMetadataProp_1
0x180084484  mov     r8b, al; bool
0x180084487  mov     rdx, [rbp+300h+var_2E8]; wchar_t *
0x18008448b  lea     rcx, [rbp+300h+var_2C0]; this
0x18008448f  call    ?SetLogFilePath@ChannelConfigWriteData@@QEAAXPEB_W_N@Z; ChannelConfigWriteData::SetLogFilePath(wchar_t const *,bool)
0x180084494  mov     rcx, rsi; this
0x180084497  call    ?GetMaxSize@ChannelConfigReader@@QEBA_KXZ; ChannelConfigReader::GetMaxSize(void)
0x18008449c  mov     qword ptr [rsp+400h+var_3C8.Data4], rax
0x1800844a1  lea     r8, [rsp+400h+var_3C8.Data4]
0x1800844a6  mov     edx, 8
0x1800844ab  mov     rcx, rbx
0x1800844ae  call    ReadModifiedMetadataProp_2
0x1800844b3  mov     rcx, qword ptr [rsp+400h+var_3C8.Data4]
0x1800844b8  mov     [rbp+300h+var_1E8], rcx
0x1800844bf  mov     cl, [rbp+300h+var_1D0]
0x1800844c5  and     cl, r12b
0x1800844c8  or      cl, al
0x1800844ca  mov     [rbp+300h+var_1D0], cl
0x1800844d0  mov     rcx, rsi; this
0x1800844d3  call    ?GetFileMax@ChannelConfigReader@@QEBAKXZ; ChannelConfigReader::GetFileMax(void)
0x1800844d8  mov     dword ptr [rsp+400h+var_3C8.Data4], eax
0x1800844dc  lea     r8, [rsp+400h+var_3C8.Data4]
0x1800844e1  mov     edx, 14h
0x1800844e6  mov     rcx, rbx
0x1800844e9  call    ReadModifiedMetadataProp
0x1800844ee  mov     edx, dword ptr [rsp+400h+var_3C8.Data4]
0x1800844f2  mov     cl, [rbp+300h+var_1C4]
0x1800844f8  cmp     edx, 1
0x1800844fb  ja      short loc_180084500
0x1800844fd  or      cl, 3
0x180084500  mov     [rbp+300h+var_258], edx
0x180084506  and     cl, r12b
0x180084509  or      cl, al
0x18008450b  mov     [rbp+300h+var_1C4], cl
0x180084511  mov     rcx, rsi; this
0x180084514  call    ?GetRawEnabled@ChannelConfigReader@@QEBA_NXZ; ChannelConfigReader::GetRawEnabled(void)
0x180084519  mov     [rsp+400h+var_3D0], al
0x18008451d  lea     r8, [rsp+400h+var_3D0]
0x180084522  xor     edx, edx
0x180084524  mov     rcx, rbx
0x180084527  call    ReadModifiedMetadataProp_3
0x18008452c  mov     cl, [rsp+400h+var_3D0]
0x180084530  mov     [rbp+300h+var_288], cl
0x180084533  mov     cl, [rbp+300h+var_1D8]
0x180084539  and     cl, r12b
0x18008453c  or      cl, al
0x18008453e  mov     [rbp+300h+var_1D8], cl
0x180084544  mov     rcx, rsi; this
0x180084547  call    ?GetLevel@ChannelConfigReader@@QEBAKXZ; ChannelConfigReader::GetLevel(void)
0x18008454c  mov     dword ptr [rsp+400h+var_3C8.Data4], eax
0x180084550  lea     r8, [rsp+400h+var_3C8.Data4]
0x180084555  mov     edx, 0Ah
0x18008455a  mov     rcx, rbx
0x18008455d  call    ReadModifiedMetadataProp
0x180084562  mov     dl, al
0x180084564  mov     ecx, 0FFh
0x180084569  cmp     dword ptr [rsp+400h+var_3C8.Data4], ecx
0x18008456d  ja      short loc_180084573
0x18008456f  mov     cl, [rsp+400h+var_3C8.Data4]
0x180084573  mov     [rbp+300h+var_24E], cl
0x180084579  mov     al, [rbp+300h+var_1CE]
0x18008457f  and     al, r12b
0x180084582  or      al, dl
0x180084584  mov     [rbp+300h+var_1CE], al
0x18008458a  mov     rcx, rsi; this
0x18008458d  call    ?GetKeywords@ChannelConfigReader@@QEBA_KXZ; ChannelConfigReader::GetKeywords(void)
0x180084592  mov     qword ptr [rsp+400h+var_3C8.Data4], rax
0x180084597  lea     r8, [rsp+400h+var_3C8.Data4]
0x18008459c  mov     edx, 0Bh
0x1800845a1  mov     rcx, rbx
0x1800845a4  call    ReadModifiedMetadataProp_2
0x1800845a9  mov     rcx, qword ptr [rsp+400h+var_3C8.Data4]
0x1800845ae  mov     [rbp+300h+var_280], rcx
0x1800845b5  mov     cl, [rbp+300h+var_1CD]
0x1800845bb  and     cl, r12b
0x1800845be  or      cl, al
  ... truncated ...
```
