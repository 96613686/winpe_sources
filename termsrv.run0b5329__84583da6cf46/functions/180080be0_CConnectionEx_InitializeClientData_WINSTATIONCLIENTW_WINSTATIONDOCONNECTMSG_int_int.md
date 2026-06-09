# CConnectionEx::InitializeClientData(_WINSTATIONCLIENTW *,_WINSTATIONDOCONNECTMSG *,int *,int *)

- ea: `0x180080be0`
- end: `0x1800821a6`
- name: `?InitializeClientData@CConnectionEx@@UEAAJPEAU_WINSTATIONCLIENTW@@PEAU_WINSTATIONDOCONNECTMSG@@PEAH2@Z`
- size: `5574`
- prototype: `__int64 __fastcall(CConnectionEx *__hidden this, struct _WINSTATIONCLIENTW *, struct _WINSTATIONDOCONNECTMSG *, int *, int *)`
- caller_count: `0`
- callee_count: `45`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001284`
- `0x180001688`
- `0x180001f18`
- `0x1800020c8`
- `0x18000225c`
- `0x180002304`
- `0x180002544`
- `0x18000396c`
- `0x180003a18`
- `0x180003b5c`
- `0x18000a210`
- `0x18000c2f0`
- `0x180013150`
- `0x180013ec4`
- `0x1800148f0`
- `0x180017608`
- `0x1800287e0`
- `0x1800288f4`
- `0x180028954`
- `0x1800321f0`
- `0x1800330c4`
- `0x1800637f8`
- `0x180063dc8`
- `0x18006459c`
- `0x1800646f4`
- `0x180064894`
- `0x180064a10`
- `0x180065af8`
- `0x1800792cc`
- `0x1800799c8`
- `0x18007df30`
- `0x18007dfc8`
- `0x18007e044`
- `0x18007fae0`
- `0x1800806c0`
- `0x180080be0`
- `0x1800825e4`
- `0x1800840d0`
- `0x180084670`
- `0x180085290`
- `0x1800852b8`
- `0x180086bdc`
- `0x1800c4da0`
- `0x1800c4e00`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008160a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081fec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008160a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081fec`
- `SspiCli!LsaConnectUntrusted` at `0x1800819ec`
- `SspiCli!LsaConnectUntrusted` at `0x1800819ec`
- `SspiCli!LogonUserExExW` at `0x1800815f4`
- `SspiCli!LogonUserExExW` at `0x180081ee6`
- `SspiCli!LogonUserExExW` at `0x180081fd6`
- `SspiCli!LogonUserExExW` at `0x1800815f4`
- `SspiCli!LogonUserExExW` at `0x180081ee6`
- `SspiCli!LogonUserExExW` at `0x180081fd6`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180081d6c`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180081d6c`
- `SspiCli!LsaLogonUser` at `0x180081c3d`
- `SspiCli!LsaLogonUser` at `0x180081c3d`
- `WTSAPI32!WTSFreeMemoryExW` at `0x180081713`
- `WTSAPI32!WTSFreeMemoryExW` at `0x180081713`

## string_xrefs

- `0x180080d75`: `this->ptrIWRdsProtocolConnection->GetClientData`
- `0x180080f43`: `MergeUserConfig`
- `0x18008109e`: `this->ptrIWRdsProtocolConnection->QueryProperty(PROPERTY_TYPE_RESTRICTED_LOGON)`
- `0x18008193a`: `Terminal Services API`
- `0x180081b20`: `FastReconnectAADTipTest::reason::GetSecurityFilterClientTokenFailed`
- `0x180081c80`: `FastReconnectAADTipTest::reason::GetSecurityFilterClientTokenFailed`
- `0x180081b5a`: `CConnectionEx::GetSecurityFilterClientToken failed`

## pseudocode

```c
__int64 __fastcall CConnectionEx::InitializeClientData(
        CConnectionEx *this,
        struct _WINSTATIONCLIENTW *a2,
        struct _WINSTATIONDOCONNECTMSG *a3,
        int *a4,
        int *a5)
{
  int v9; // r15d
  unsigned int v10; // ecx
  signed int InstanceOfRemoteConnectionManager; // esi
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  char *v15; // rax
  char *v16; // rdx
  unsigned int v17; // r15d
  int v18; // ecx
  __int64 v19; // rcx
  int v20; // ecx
  __int64 v21; // rcx
  int v22; // ecx
  __int64 v23; // rcx
  int v24; // eax
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rcx
  int v28; // eax
  int v29; // r8d
  int v30; // r9d
  int v31; // ecx
  __int64 v32; // rcx
  int v33; // eax
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  int v37; // eax
  const unsigned __int16 *v38; // rbx
  int v39; // eax
  struct _QUOTA_LIMITS *p_Quotas; // rcx
  int v41; // r8d
  int v42; // r9d
  __int64 v43; // rax
  DWORD LastError; // eax
  __int64 v45; // rcx
  struct _QUOTA_LIMITS *v46; // rax
  int (__fastcall ***v47)(_QWORD, GUID *, __int64 *); // rcx
  int (__fastcall **v48)(_QWORD, GUID *, __int64 *); // rax
  __int64 v49; // rsi
  int (__fastcall *v50)(__int64, PVOID *); // r14
  PVOID v51; // rbx
  int v52; // r9d
  __int64 v53; // rcx
  _QWORD *v54; // r14
  int InstanceOfSecFilterCredentials; // eax
  int v56; // r8d
  int v57; // r9d
  __int64 v58; // rcx
  int *v59; // rbx
  int v60; // eax
  __int64 v61; // rbx
  int v62; // ecx
  int v63; // r8d
  int v64; // r9d
  PVOID AuthenticationInformation; // r14
  NTSTATUS v66; // r15d
  const char *v67; // rdx
  const char *v68; // r8
  char v69; // cl
  int v70; // ecx
  int v71; // r8d
  int v72; // r9d
  int InstanceOfWtsSerializedUserCredentials; // eax
  const char *v74; // rax
  const char *v75; // r8
  char v76; // cl
  int v77; // ecx
  int v78; // r8d
  int v79; // r9d
  NTSTATUS v80; // eax
  int v81; // ecx
  int v82; // r8d
  int v83; // r9d
  const char *v84; // rax
  const char *v85; // r8
  char v86; // cl
  int v87; // eax
  int v88; // ecx
  int v89; // r8d
  int v90; // r9d
  __int64 v91; // rax
  _BYTE *v92; // rcx
  int v93; // eax
  int v94; // ecx
  unsigned __int16 *v95; // rcx
  int InstanceOfSmartCardCredentials; // eax
  unsigned __int16 *v97; // r8
  int InstanceOfPasswordCredentials; // eax
  __int64 v99; // rax
  int v100; // eax
  const unsigned __int16 *v101; // r8
  __int64 v102; // rax
  DWORD v103; // eax
  __int64 v104; // rcx
  int v105; // eax
  int v106; // r8d
  int v107; // r9d
  __int64 v108; // rdx
  __int64 v109; // rcx
  char *v110; // rax
  __int64 v111; // rax
  __int64 v112; // r8
  unsigned __int16 *v113; // rcx
  __int64 v114; // r8
  WCHAR *Password; // rcx
  char *v116; // rcx
  char *v117; // rdi
  int v119; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v120[4]; // [rsp+74h] [rbp-8Ch] BYREF
  void *Token; // [rsp+78h] [rbp-88h] BYREF
  int v122; // [rsp+80h] [rbp-80h] BYREF
  const char *v123; // [rsp+88h] [rbp-78h] BYREF
  void *LsaHandle; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v125[8]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v126; // [rsp+A0h] [rbp-60h] BYREF
  const char *v127; // [rsp+A8h] [rbp-58h] BYREF
  const char *v128; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v129; // [rsp+B8h] [rbp-48h] BYREF
  int SubStatus; // [rsp+BCh] [rbp-44h] BYREF
  ULONG ProfileBufferLength; // [rsp+C0h] [rbp-40h] BYREF
  PVOID pMemory; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v133; // [rsp+D0h] [rbp-30h] BYREF
  const char *v134; // [rsp+D8h] [rbp-28h] BYREF
  TSCompatShim *v135; // [rsp+E0h] [rbp-20h] BYREF
  int *v136; // [rsp+E8h] [rbp-18h]
  struct IRemoteConnectionManager *v137; // [rsp+F0h] [rbp-10h] BYREF
  const char *v138; // [rsp+F8h] [rbp-8h] BYREF
  const char *v139; // [rsp+100h] [rbp+0h] BYREF
  PVOID ProfileBuffer; // [rsp+108h] [rbp+8h] BYREF
  struct _GUID Buf1; // [rsp+110h] [rbp+10h] BYREF
  ULONG AuthenticationInformationLength[2]; // [rsp+120h] [rbp+20h] BYREF
  PVOID v143; // [rsp+128h] [rbp+28h]
  __int64 v144; // [rsp+130h] [rbp+30h]
  struct _LUID LogonId; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v146[56]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v147; // [rsp+178h] [rbp+78h]
  struct _TOKEN_SOURCE SourceContext; // [rsp+180h] [rbp+80h] BYREF
  _DWORD v149[6]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v150; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v151; // [rsp+1B8h] [rbp+B8h]
  unsigned __int16 v152[256]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 v153[256]; // [rsp+3C0h] [rbp+2C0h] BYREF
  unsigned __int16 v154[256]; // [rsp+5C0h] [rbp+4C0h] BYREF
  struct _WTS_CLIENT_DATA v155; // [rsp+7C0h] [rbp+6C0h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+1640h] [rbp+1540h] BYREF

  v136 = a5;
  memset_0(v152, 0, 0x600u);
  v135 = 0;
  v129 = 0;
  pMemory = 0;
  v133 = 0;
  memset_0(&v155, 0, sizeof(v155));
  v137 = 0;
  if ( *((_QWORD *)this + 201) )
  {
    if ( (unsigned int)(*((_DWORD *)this + 4470) - 2) <= 1 )
    {
      Buf1 = 0;
      CConnectionEx::GetConnectionGUIDFromProtocol(this, &Buf1);
      if ( !memcmp_0(&Buf1, &TERMINAL_TYPE_RDP_REMOTEAPP, 0x10u) )
        *((_DWORD *)this + 2432) |= 8u;
    }
  }
  v9 = *((_DWORD *)this + 2432);
  v155.fDisableCpm = (v9 & 0x20000000) != 0;
  v155.fDisableCdm = (v9 & 0x40000000) != 0;
  v155.fDisableCcm = v9 < 0;
  v155.fDisableLPT = *((_BYTE *)this + 9732) & 1;
  v10 = *((_DWORD *)this + 2433);
  v155.fDisableClip = (v10 & 2) != 0;
  v155.fDisablePNP = (v10 & 0x800) != 0;
  v155.fInheritAutoLogon = v9 & 1;
  v155.fInheritInitialProgram = ((unsigned int)v9 >> 3) & 1;
  v155.fInheritColorDepth = (v10 >> 8) & 1;
  InstanceOfRemoteConnectionManager = (*(__int64 (__fastcall **)(_QWORD, struct _WTS_CLIENT_DATA *))(**((_QWORD **)this + 199) + 40LL))(
                                        *((_QWORD *)this + 199),
                                        &v155);
  if ( InstanceOfRemoteConnectionManager >= 0 )
  {
    InstanceOfRemoteConnectionManager = GetInstanceOfRemoteConnectionManager(&v137);
    if ( InstanceOfRemoteConnectionManager < 0 )
    {
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_194;
      Token = "InitializeClientData";
      v15 = "GetInstanceOfRemoteConnectionManager";
      v16 = (char *)qword_18010F038;
      goto LABEL_8;
    }
    if ( (*(unsigned int (__fastcall **)(struct IRemoteConnectionManager *))(*(_QWORD *)v137 + 400LL))(v137) )
    {
      v155.DisplayDriverName[0] = 0;
      v155.DisplayDeviceName[0] = 0;
    }
    *((_DWORD *)this + 4014) = 1;
    memset_0(a3, 0, 0x468u);
    InstanceOfRemoteConnectionManager = CHelper::ConvertWTSClientDataToWRdsConnectionSetting(
                                          (struct _WRDS_CONNECTION_SETTINGS *)((char *)this + 12272),
                                          &v155);
    if ( InstanceOfRemoteConnectionManager < 0 )
    {
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_194;
      Token = "InitializeClientData";
      v15 = "CHelper::ConvertWTSClientDataToWRdsConnectionSetting";
      v16 = byte_18010EFF3;
      goto LABEL_8;
    }
    InstanceOfRemoteConnectionManager = CHelper::ConvertWRdsConnectionSettingToWinStationClient(
                                          a2,
                                          a3,
                                          (struct _WRDS_CONNECTION_SETTINGS *)((char *)this + 12272));
    if ( InstanceOfRemoteConnectionManager < 0 )
    {
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_194;
      Token = "InitializeClientData";
      v15 = "CHelper::ConvertWRdsConnectionSettingToWinStationClient";
      v16 = (char *)&word_18010EFAE;
      goto LABEL_8;
    }
    v17 = (unsigned int)v9 >> 12;
    *((_DWORD *)this + 2432) &= 0xFFFFFFF6;
    *((_DWORD *)this + 2432) |= v155.fInheritAutoLogon & 1 | (8 * (v155.fInheritInitialProgram & 1));
    *((_DWORD *)this + 2433) &= ~0x100u;
    *((_DWORD *)this + 2433) |= (v155.fInheritColorDepth & 1) << 8;
    InstanceOfRemoteConnectionManager = CConnectionEx::MergeUserConfig(this, a2, a3);
    if ( InstanceOfRemoteConnectionManager < 0 )
    {
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_194;
      Token = "InitializeClientData";
      v15 = "MergeUserConfig";
      v16 = byte_18010EF69;
      goto LABEL_8;
    }
    *((_DWORD *)this + 2432) = (v155.fDisableCcm << 31)
                             | ((*((_DWORD *)this + 2432)
                               ^ (*((_DWORD *)this + 2432)
                                ^ (v155.fDisableCpm << 29))
                               & 0x20000000)
                              & 0x3FFFFFFF
                              ^ (v155.fDisableCdm << 30))
                             & 0x7FFFFFFF;
    v18 = *((_DWORD *)this + 2433) ^ (*((_DWORD *)this + 2433) ^ v155.fDisableLPT) & 1;
    *((_DWORD *)this + 2433) = v18
                             ^ (*((_BYTE *)this + 9732)
                              ^ (*((_BYTE *)this + 9732)
                               ^ v155.fDisableLPT)
                              & 1
                              ^ (unsigned __int8)(2 * v155.fDisableClip))
                             & 2
                             ^ (*((_WORD *)this + 4866)
                              ^ (*((_WORD *)this + 4866)
                               ^ v155.fDisableLPT)
                              & 1
                              ^ (*((_BYTE *)this + 9732)
                               ^ (*((_BYTE *)this + 9732)
                                ^ v155.fDisableLPT)
                               & 1
                               ^ (unsigned __int8)(2 * v155.fDisableClip))
                              & 2
                              ^ (unsigned __int16)(v155.fDisablePNP << 11))
                             & 0x800;
    if ( (unsigned int)dword_180128170 > 4 )
    {
      Token = (void *)*((_QWORD *)this + 201);
      LsaHandle = "Init client data0";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v18,
        (unsigned int)byte_18010EF2B,
        v12,
        v13,
        (__int64)&LsaHandle,
        (__int64)&Token);
    }
    if ( *((_QWORD *)this + 201) )
    {
      memset(v149, 0, sizeof(v149));
      v19 = *((_QWORD *)this + 199);
      SourceContext = (struct _TOKEN_SOURCE)PROPERTY_TYPE_GET_RESTRICTED_LOGON;
      InstanceOfRemoteConnectionManager = (*(__int64 (__fastcall **)(__int64, struct _TOKEN_SOURCE *, _QWORD, __int64, _QWORD, _DWORD *))(*(_QWORD *)v19 + 192LL))(
                                            v19,
                                            &SourceContext,
                                            0,
                                            1,
                                            0,
                                            v149);
      if ( InstanceOfRemoteConnectionManager < 0 )
      {
        if ( (unsigned int)dword_180128170 <= 3 )
          goto LABEL_194;
        Token = "InitializeClientData";
        v15 = "this->ptrIWRdsProtocolConnection->QueryProperty(PROPERTY_TYPE_RESTRICTED_LOGON)";
        v16 = (char *)&word_18010EEE6;
        goto LABEL_8;
      }
      v20 = v149[2] != 0 ? 0x1000 : 0;
      *(_DWORD *)a2 &= ~0x1000u;
      *(_DWORD *)a2 |= v20;
      v21 = *((_QWORD *)this + 199);
      SourceContext = (struct _TOKEN_SOURCE)PROPERTY_TYPE_GET_REDIRECTED_AUTHENTICATION;
      if ( (*(int (__fastcall **)(__int64, struct _TOKEN_SOURCE *, _QWORD, __int64, _QWORD, _DWORD *))(*(_QWORD *)v21 + 192LL))(
             v21,
             &SourceContext,
             0,
             1,
             0,
             v149) >= 0 )
      {
        v22 = v149[2] != 0 ? 0x2000 : 0;
        *(_DWORD *)a2 &= ~0x2000u;
        *(_DWORD *)a2 |= v22;
      }
      else
      {
        *(_DWORD *)a2 &= ~0x2000u;
      }
      *((_WORD *)this + 9312) = -1;
      v23 = *((_QWORD *)this + 199);
      SourceContext = (struct _TOKEN_SOURCE)PROPERTY_TYPE_GET_STACK_SC_CLIP_LEVEL;
      v24 = (*(__int64 (__fastcall **)(__int64, struct _TOKEN_SOURCE *, _QWORD, __int64, _QWORD, _DWORD *))(*(_QWORD *)v23 + 192LL))(
              v23,
              &SourceContext,
              0,
              1,
              0,
              v149);
      if ( v24 >= 0 )
      {
        if ( (unsigned __int8)(LOBYTE(v149[2]) - 5) > 0xF9u )
        {
          *((_BYTE *)this + 18624) = v149[2];
        }
        else if ( (unsigned int)dword_180128170 > 2 )
        {
          v120[0] = v149[2];
          Token = "The stack SC ClipLevel is out-of-range, reset to use default value";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>>(
            v149[2],
            (unsigned int)byte_18010EE79,
            v25,
            v26,
            (__int64)&Token,
            (__int64)v120);
        }
      }
      else if ( (unsigned int)dword_180128170 > 3 )
      {
        v119 = v24;
        Token = "Failed to query stack SC ClipLevel, non-fatal";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_180128170,
          (unsigned int)&word_18010EEB6,
          v25,
          v26,
          (__int64)&Token,
          (__int64)&v119);
      }
      v27 = *((_QWORD *)this + 199);
      SourceContext = (struct _TOKEN_SOURCE)PROPERTY_TYPE_GET_STACK_CS_CLIP_LEVEL;
      v28 = (*(__int64 (__fastcall **)(__int64, struct _TOKEN_SOURCE *, _QWORD, __int64, _QWORD, _DWORD *))(*(_QWORD *)v27 + 192LL))(
              v27,
              &SourceContext,
              0,
              1,
              0,
              v149);
      if ( v28 >= 0 )
      {
        v31 = v149[2];
        if ( (unsigned __int8)(LOBYTE(v149[2]) - 5) > 0xF9u )
        {
          *((_BYTE *)this + 18625) = v149[2];
        }
        else if ( (unsigned int)dword_180128170 > 2 )
        {
          v120[0] = v149[2];
          Token = "The stack CS ClipLevel is out-of-range, reset to use default value";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>>(
            v149[2],
            (unsigned int)&dword_18010EE0C,
            v29,
            v30,
            (__int64)&Token,
            (__int64)v120);
        }
      }
      else
      {
        v31 = dword_180128170;
        if ( (unsigned int)dword_180128170 > 3 )
        {
          v119 = v28;
          Token = "Failed to query stack CS ClipLevel, non-fatal";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            dword_180128170,
            (unsigned int)byte_18010EE49,
            v29,
            v30,
            (__int64)&Token,
            (__int64)&v119);
        }
      }
      if ( (unsigned int)dword_180128170 > 4 )
      {
        v120[0] = *((_BYTE *)this + 18625);
        v125[0] = *((_BYTE *)this + 18624);
        Token = "Got stack clipboard levels";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
          v31,
          (unsigned int)byte_18010EDC3,
          v29,
          v30,
          (__int64)&Token,
          (__int64)v125,
          (__int64)v120);
      }
      if ( *((_QWORD *)this + 201) )
      {
        if ( (unsigned int)dword_180128170 > 5 )
        {
          Token = "Microsoft RDP Stack detected, assuming Basic Fast Reconnect by default";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v31,
            (unsigned int)qword_18010EDA0,
            v29,
            v30,
            (__int64)&Token);
        }
        *((_DWORD *)this + 4620) = 1;
      }
    }
    v150 = 0;
    v151 = 0;
    v32 = *((_QWORD *)this + 199);
    SourceContext = (struct _TOKEN_SOURCE)PROPERTY_TYPE_GET_FAST_RECONNECT;
    v33 = (*(__int64 (__fastcall **)(__int64, struct _TOKEN_SOURCE *, _QWORD, __int64, _QWORD, __int128 *))(*(_QWORD *)v32 + 192LL))(
            v32,
            &SourceContext,
            0,
            1,
            0,
            &v150);
    if ( v33 >= 0 )
    {
      if ( (_WORD)v150 == 1 )
      {
        if ( DWORD2(v150) )
        {
          if ( DWORD2(v150) == 1 )
          {
            *((_DWORD *)this + 4620) = 1;
          }
          else if ( DWORD2(v150) == 2 )
          {
            *((_DWORD *)this + 4620) = 2;
          }
          else if ( (unsigned int)dword_180128170 > 2 )
          {
            v119 = *((_DWORD *)this + 4620);
            v122 = DWORD2(v150);
            Token = "Unsupported Fast Reconnect type returned by stack. Default value set";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v34,
              (unsigned int)&word_18010ED36,
              v35,
              v36,
              (__int64)&Token,
              (__int64)&v122,
              (__int64)&v119);
          }
        }
        else
        {
          *((_DWORD *)this + 4620) = 0;
        }
        if ( (unsigned int)dword_180128170 > 5 )
        {
          v122 = *((_DWORD *)this + 4620);
          v119 = DWORD2(v150);
          Token = "Setting eFastReconnectType from stack";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v34,
            (unsigned int)&dword_18010ECF4,
            v35,
            v36,
            (__int64)&Token,
            (__int64)&v119,
            (__int64)&v122);
        }
      }
      else if ( (unsigned int)dword_180128170 > 2 )
      {
        Token = "Fast Reconnect property from stack wasn't a ULONG";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v34,
          (unsigned int)byte_18010ECD1,
          v35,
          v36,
          (__int64)&Token);
      }
    }
    else if ( (unsigned int)dword_180128170 > 3 )
    {
      v119 = v33;
      Token = "Failed to query fast reconnect property";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_180128170,
        (unsigned int)qword_18010ED78,
        v35,
        v36,
        (__int64)&Token,
        (__int64)&v119);
    }
    v37 = *((_DWORD *)this + 2432);
    if ( (v37 & 1) == 0 )
    {
      v38 = 0;
      if ( (v37 & 0x1000) == 0 )
      {
        v39 = CAutologonPassword::Retrieve((unsigned __int8 *)&Quotas, (const unsigned __int16 *)this + 848);
        p_Quotas = &Quotas;
        if ( v39 < 0 )
          p_Quotas = 0;
        v38 = (const unsigned __int16 *)p_Quotas;
      }
      InstanceOfRemoteConnectionManager = CCredentialsFactory::GetInstanceOfPasswordCredentials(
                                            (const unsigned __int16 *)this + 4868,
                                            (const unsigned __int16 *)this + 4889,
                                            v38,
                                            (struct ICredentials **)this + 2005);
      if ( *((_DWORD *)this + 4620) != 1 )
        goto LABEL_84;
      if ( !v38 )
        goto LABEL_81;
      v43 = -1;
      do
        ++v43;
      while ( v38[v43] );
      if ( v43 )
      {
        if ( (unsigned int)LogonUserExExW(
                             (char *)this + 9736,
                             (char *)this + 9778,
                             v38,
                             3,
                             0,
                             0,
                             (char *)this + 17952,
                             0,
                             0,
                             0,
                             0) )
        {
LABEL_84:
          v45 = 64;
          v46 = &Quotas;
          do
          {
            LOBYTE(v46->PagedPoolLimit) = 0;
            v46 = (struct _QUOTA_LIMITS *)((char *)v46 + 1);
            --v45;
          }
          while ( v45 );
          if ( InstanceOfRemoteConnectionManager < 0 && (unsigned int)dword_180128170 > 3 )
          {
            Token = "InitializeClientData";
            v122 = InstanceOfRemoteConnectionManager;
            LsaHandle = "GetInstanceOfPasswordCredentials";
            v123 = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              0,
              (unsigned int)&dword_18010EC8C,
              v41,
              v42,
              (__int64)&v123,
              (__int64)&LsaHandle,
              (__int64)&v122,
              (__int64)&Token);
          }
          goto LABEL_194;
        }
        if ( (g_DebugTraceComponent & 4) != 0 )
        {
          LastError = GetLastError();
          _DbgPrintMessage(2, "Failed to logon using clear text, error code 0x%08x", LastError);
        }
      }
      else
      {
LABEL_81:
        if ( (g_DebugTraceComponent & 4) != 0 )
          _DbgPrintMessage(2, "Password length is zero, disabling fast reconnect");
      }
      *((_DWORD *)this + 4620) = 0;
      goto LABEL_84;
    }
    v126 = 0;
    v47 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 199);
    v48 = *v47;
    v126 = 0;
    if ( (*v48)(v47, &GUID_c2bd9b66_4a76_4701_b6a3_bfafc1482169, &v126) >= 0 )
    {
      v49 = v126;
      v50 = *(int (__fastcall **)(__int64, PVOID *))(*(_QWORD *)v126 + 216LL);
      v51 = pMemory;
      if ( pMemory )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&Token);
        WTSFreeMemoryExW((WTS_TYPE_CLASS)4, v51, 1u);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&Token);
      }
      pMemory = 0;
      if ( v50(v49, &pMemory) >= 0 )
        goto LABEL_96;
    }
    v53 = *((_QWORD *)this + 201);
    if ( v53 )
    {
      if ( (*(int (__fastcall **)(__int64, TSCompatShim **, unsigned int *, unsigned int *))(*(_QWORD *)v53 + 32LL))(
             v53,
             &v135,
             &v129,
             &v133) >= 0 )
      {
LABEL_96:
        if ( v129 || pMemory )
        {
          if ( (v17 & 1) != 0 && (*(_DWORD *)a2 & 0x800) != 0 )
          {
            CConnectionEx::SetErrorInfo(this, 0xAu, 0);
            InstanceOfRemoteConnectionManager = -2147024891;
            _DbgPrintMessage(8, "Disconnecting because fresh credential is required");
LABEL_193:
            SmartPtr<IWRdsWddmIddProps1>::~SmartPtr<IWRdsWddmIddProps1>(&v126);
            goto LABEL_194;
          }
          if ( v129 )
          {
            v54 = (_QWORD *)((char *)this + 16040);
            InstanceOfSecFilterCredentials = CCredentialsFactory::GetInstanceOfSecFilterCredentials(
                                               (unsigned __int8 *)v135,
                                               v129,
                                               v133,
                                               v52,
                                               1,
                                               (struct ICredentials **)this + 2005);
            InstanceOfRemoteConnectionManager = InstanceOfSecFilterCredentials;
            if ( InstanceOfSecFilterCredentials < 0 )
            {
              _DbgPrintMessage(
                8,
                "GetInstanceOfSecFilterCredentials failed: 0x%x in %s",
                (unsigned int)InstanceOfSecFilterCredentials,
                "CConnectionEx::InitializeClientData");
              goto LABEL_193;
            }
            v135 = 0;
            v129 = 0;
          }
          else
          {
            if ( !pMemory )
            {
              InstanceOfRemoteConnectionManager = -2147418113;
              _DbgPrintMessage(8, "Unexpected credentials buffer!");
              goto LABEL_193;
            }
            v54 = (_QWORD *)((char *)this + 16040);
            InstanceOfWtsSerializedUserCredentials = CCredentialsFactory::GetInstanceOfWtsSerializedUserCredentials(
                                                       (struct _WTS_SERIALIZED_USER_CREDENTIAL **)&pMemory,
                                                       (struct ICredentials **)this + 2005);
            InstanceOfRemoteConnectionManager = InstanceOfWtsSerializedUserCredentials;
            if ( InstanceOfWtsSerializedUserCredentials < 0 )
            {
              _DbgPrintMessage(
                8,
                "GetInstanceOfSerializedUserCredentials failed: 0x%x in %s",
                (unsigned int)InstanceOfWtsSerializedUserCredentials,
                "CConnectionEx::InitializeClientData");
              goto LABEL_193;
            }
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FastReconnectWithAADCreds>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FastReconnectWithAADCreds>::GetImpl'::`2'::impl) )
          {
            v58 = *v54;
            v59 = v136;
            if ( *v54 )
            {
              v60 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v58 + 40LL))(v58, a4, v136);
              LODWORD(v58) = dword_180128170;
              if ( (unsigned int)dword_180128170 > 5 )
              {
                v122 = InstanceOfRemoteConnectionManager;
                v119 = v60;
                LODWORD(v127) = *a4;
                Token = "GetDisconnectOnLockPolicy returned";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  dword_180128170,
                  (unsigned int)&unk_18010EC38,
                  v56,
                  v57,
                  (__int64)&Token,
                  (__int64)&v127,
                  (__int64)&v119,
                  (__int64)&v122);
              }
            }
            if ( (unsigned int)dword_180128170 > 5 )
            {
              Token = "Feature_FastReconnectWithAADCreds is enabled";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                v58,
                (unsigned int)byte_18010EC15,
                v56,
                v57,
                (__int64)&Token);
            }
            if ( *v59 )
            {
              v123 = 0;
              tip2::tip_test<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>>::start_and_watch_errors(
                &v123,
                v146);
              wil::com_ptr_t<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>,wil::err_returncode_policy>(&v123);
              v61 = v147;
              v123 = (const char *)v147;
              if ( v147 )
                _InterlockedIncrement((volatile signed __int32 *)(v147 + 272));
              tip2::test_watcher<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>>::~test_watcher<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>>(v146);
              if ( (unsigned int)dword_180128170 > 5 )
              {
                v127 = "Using AAD creds, going to try to use fast reconnect";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  v62,
                  (unsigned int)word_18010EBF2,
                  v63,
                  v64,
                  (__int64)&v127);
              }
              strcpy((char *)v149, "Terminal Services API");
              *(_QWORD *)&Buf1.Data1 = 1441814;
              *(_QWORD *)Buf1.Data4 = v149;
              strcpy(SourceContext.SourceName, "termsrv");
              SourceContext.SourceIdentifier = 0;
              ProfileBuffer = 0;
              ProfileBufferLength = 0;
              LogonId = 0;
              memset(&Quotas, 0, sizeof(Quotas));
              SubStatus = 0;
              LsaHandle = 0;
              Token = 0;
              *(_QWORD *)AuthenticationInformationLength = 0;
              v143 = 0;
              v144 = 0;
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v54 + 48LL))(*v54);
              (*(void (__fastcall **)(_QWORD, ULONG *))(*(_QWORD *)*v54 + 24LL))(*v54, AuthenticationInformationLength);
              AuthenticationInformation = v143;
              v66 = LsaConnectUntrusted(&LsaHandle);
              if ( v66 < 0 )
              {
                InstanceOfRemoteConnectionManager = -2147467259;
                v67 = "FastReconnectAADTipTest::reason::LsaConnectUntrustedFailed";
                v68 = "FastReconnectAADTipTest::reason::LsaConnectUntrustedFailed";
                v69 = 70;
                do
                {
                  ++v67;
                  if ( v69 == 58 )
                    v68 = v67;
                  v69 = *v67;
                }
                while ( *v67 );
                tip2::tip_test<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>>::complete_and_fail(
                  &v123,
                  0,
                  v68);
                if ( (unsigned int)dword_180128170 > 2 )
                {
                  LODWORD(v127) = v66;
                  v138 = "LsaConnectUntrusted failed";
                  v139 = "InitializeClientData";
                  v122 = 1381;
                  v134 = "clientcore\\termsrv\\newsvc\\remote\\extcon.cpp";
                  v119 = -2147467259;
                  v128 = "Error HResult failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                    v70,
                    (unsigned int)qword_18010EB98,
                    v71,
                    v72,
                    (__int64)&v128,
                    (__int64)&v119,
                    (__int64)&v134,
                    (__int64)&v122,
                    (__int64)&v139,
                    (__int64)&v138,
                    (__int64)&v127);
                }
LABEL_122:
                wil::com_ptr_t<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>,wil::err_returncode_policy>(&v123);
                goto LABEL_193;
              }
              InstanceOfRemoteConnectionManager = CConnectionEx::GetSecurityFilterClientToken(this, 0, &Token);
              if ( InstanceOfRemoteConnectionManager < 0 )
              {
                v74 = "FastReconnectAADTipTest::reason::GetSecurityFilterClientTokenFailed";
                v75 = "FastReconnectAADTipTest::reason::GetSecurityFilterClientTokenFailed";
                v76 = 70;
                do
                {
                  ++v74;
                  if ( v76 == 58 )
                    v75 = v74;
                  v76 = *v74;
                }
                while ( *v74 );
                tip2::tip_test<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>>::complete_and_fail(
                  &v123,
                  1,
                  v75);
                if ( (unsigned int)dword_180128170 > 2 )
                {
                  v128 = "CConnectionEx::GetSecurityFilterClientToken failed";
                  v134 = "InitializeClientData";
                  LODWORD(v127) = 1387;
                  v139 = "clientcore\\termsrv\\newsvc\\remote\\extcon.cpp";
                  v122 = InstanceOfRemoteConnectionManager;
                  v138 = "Error HResult failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    v77,
                    (unsigned int)byte_18010EB49,
                    v78,
                    v79,
                    (__int64)&v138,
                    (__int64)&v122,
                    (__int64)&v139,
                    (__int64)&v127,
                    (__int64)&v134,
                    (__int64)&v128);
                }
                goto LABEL_122;
              }
              v80 = LsaLogonUser(
                      LsaHandle,
                      (PLSA_STRING)&Buf1,
                      Network,
                      0,
                      AuthenticationInformation,
                      AuthenticationInformationLength[1],
                      0,
                      &SourceContext,
                      &ProfileBuffer,
                      &ProfileBufferLength,
                      &LogonId,
                      &Token,
                      &Quotas,
                      &SubStatus);
              if ( v80 >= 0 )
              {
                InstanceOfRemoteConnectionManager = 0;
                if ( (unsigned int)dword_180128170 > 4 )
                {
                  LODWORD(v127) = v80;
                  v122 = 0;
                  v128 = "LsaLogonuser succeeded, setting fast reconnect type to basic";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                    v81,
                    (unsigned int)qword_18010EAE8,
                    v82,
                    v83,
                    (__int64)&v128,
                    (__int64)&v122,
                    (__int64)&v127);
                }
                if ( (unsigned int)dword_180128170 > 5
                  && (unsigned __int8)tlgKeywordOn(&dword_180128170, 0x400000000000LL) )
                {
                  v128 = "LsaLogonUser succeeded with AAD creds";
                  v134 = (const char *)0x2000000;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
                    v88,
                    (unsigned int)word_18010EAAA,
                    v89,
                    v90,
                    (__int64)&v134,
                    (__int64)&v128);
                }
                v87 = 1;
              }
              else
              {
                if ( (unsigned int)dword_180128170 > 2 )
                {
                  LODWORD(v127) = v80;
                  v128 = "LsaLogonUser failed, set EFastReconnectType to None";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                    dword_180128170,
                    (unsigned int)byte_18010EB1B,
                    v82,
                    v83,
                    (__int64)&v128,
                    (__int64)&v127);
                }
                v84 = "FastReconnectAADTipTest::reason::GetSecurityFilterClientTokenFailed";
                v85 = "FastReconnectAADTipTest::reason::GetSecurityFilterClientTokenFailed";
                v86 = 70;
                do
                {
                  ++v84;
                  if ( v86 == 58 )
                    v85 = v84;
                  v86 = *v84;
                }
                while ( *v84 );
                tip2::tip_test<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>>::complete_and_fail(
                  &v123,
                  1,
                  v85);
                v87 = 0;
              }
              *((_DWORD *)this + 4620) = v87;
              if ( LsaHandle )
                LsaDeregisterLogonProcess(LsaHandle);
              v91 = AuthenticationInformationLength[1];
              v92 = v143;
              if ( AuthenticationInformationLength[1] )
              {
                do
                {
                  *v92++ = 0;
                  --v91;
                }
                while ( v91 );
              }
              if ( v61 )
              {
                wil::EnterCriticalSection(&v128, v61 + 200);
                tip2::details::shared_data<0,0,0>::complete_helper(v61 + 8);
                wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v128);
              }
              wil::com_ptr_t<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>,wil::err_returncode_policy>(&v123);
            }
          }
          *((_DWORD *)this + 4332) = 1;
          goto LABEL_193;
        }
      }
    }
    v93 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 199) + 56LL))(
            *((_QWORD *)this + 199),
            v152);
    v94 = *((_DWORD *)this + 2432) & 0x1000;
    if ( v93 < 0 )
    {
      if ( !v94 && (*((_DWORD *)this + 2433) & 0x400) != 0 )
      {
        v95 = (unsigned __int16 *)((char *)this + 9814);
LABEL_160:
        InstanceOfSmartCardCredentials = CCredentialsFactory::GetInstanceOfSmartCardCredentials(
                                           v95,
                                           (struct ICredentials **)this + 2005);
        InstanceOfRemoteConnectionManager = InstanceOfSmartCardCredentials;
        if ( InstanceOfSmartCardCredentials < 0 )
          _DbgPrintMessage(
            8,
            "GetInstanceOfSmartCardCredentials failed: 0x%x in %s",
            (unsigned int)InstanceOfSmartCardCredentials,
            "CConnectionEx::InitializeClientData");
        goto LABEL_193;
      }
      if ( v94 )
        v101 = 0;
      else
        v101 = (const unsigned __int16 *)((char *)this + 9814);
      InstanceOfPasswordCredentials = CCredentialsFactory::GetInstanceOfPasswordCredentials(
                                        (const unsigned __int16 *)this + 4868,
                                        (const unsigned __int16 *)this + 4889,
                                        v101,
                                        (struct ICredentials **)this + 2005);
      InstanceOfRemoteConnectionManager = InstanceOfPasswordCredentials;
      if ( InstanceOfPasswordCredentials < 0 )
      {
LABEL_165:
        _DbgPrintMessage(
          8,
          "GetInstanceOfPasswordCredentials failed: 0x%x in %s",
          (unsigned int)InstanceOfPasswordCredentials,
          "CConnectionEx::InitializeClientData");
        goto LABEL_193;
      }
      if ( *((_DWORD *)this + 4620) != 1 )
        goto LABEL_193;
      if ( this == (CConnectionEx *)-9814LL )
        goto LABEL_190;
      v102 = -1;
      do
        ++v102;
      while ( *((_WORD *)this + v102 + 4907) );
      if ( !v102 )
      {
LABEL_190:
        if ( (g_DebugTraceComponent & 4) != 0 )
          _DbgPrintMessage(2, "Password length is zero, disabling fast reconnect");
        *((_DWORD *)this + 4620) = 0;
        goto LABEL_193;
      }
      v100 = LogonUserExExW(
               (char *)this + 9736,
               (char *)this + 9778,
               (char *)this + 9814,
               3,
               0,
               0,
               (char *)this + 17952,
               0,
               0,
               0,
               0);
    }
    else
    {
      if ( !v94 && (*((_DWORD *)this + 2433) & 0x400) != 0 )
      {
        v95 = v153;
        goto LABEL_160;
      }
      v97 = v153;
      if ( v94 )
        v97 = 0;
      InstanceOfPasswordCredentials = CCredentialsFactory::GetInstanceOfPasswordCredentials(
                                        v152,
                                        v154,
                                        v97,
                                        (struct ICredentials **)this + 2005);
      InstanceOfRemoteConnectionManager = InstanceOfPasswordCredentials;
      if ( InstanceOfPasswordCredentials < 0 )
        goto LABEL_165;
      if ( *((_DWORD *)this + 4620) != 1 )
        goto LABEL_193;
      v99 = -1;
      do
        ++v99;
      while ( v153[v99] );
      if ( !v99 )
      {
        if ( (g_DebugTraceComponent & 4) != 0 )
          _DbgPrintMessage(2, "Password length is zero, disabling fast reconnect");
        goto LABEL_189;
      }
      v100 = LogonUserExExW(v152, v154, v153, 3, 0, 0, (char *)this + 17952, 0, 0, 0, 0);
    }
    if ( v100 )
      goto LABEL_193;
    if ( (g_DebugTraceComponent & 4) != 0 )
    {
      v103 = GetLastError();
      _DbgPrintMessage(2, "Failed to logon using clear text 2, error code 0x%08x", v103);
    }
LABEL_189:
    *((_DWORD *)this + 4620) = 0;
    goto LABEL_193;
  }
  v14 = dword_180128170;
  if ( (unsigned int)dword_180128170 > 3 )
  {
    Token = "InitializeClientData";
    v15 = "this->ptrIWRdsProtocolConnection->GetClientData";
    v16 = &byte_18010F077;
LABEL_8:
    LsaHandle = v15;
    v123 = "Warning HResult failed";
    v119 = InstanceOfRemoteConnectionManager;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v14,
      (_DWORD)v16,
      v12,
      v13,
      (__int64)&v123,
      (__int64)&LsaHandle,
      (__int64)&v119,
      (__int64)&Token);
  }
LABEL_194:
  v104 = *((_QWORD *)this + 2005);
  if ( v104 )
  {
    v105 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v104 + 40LL))(v104, a4, v136);
    if ( (unsigned int)dword_180128170 > 5 )
    {
      ProfileBufferLength = InstanceOfRemoteConnectionManager;
      SubStatus = v105;
      LODWORD(v127) = *a4;
      ProfileBuffer = "GetDisconnectOnLockPolicy returned";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        dword_180128170,
        (unsigned int)&word_18010EA56,
        v106,
        v107,
        (__int64)&ProfileBuffer,
        (__int64)&v127,
        (__int64)&SubStatus,
        (__int64)&ProfileBufferLength);
    }
  }
  if ( *((_DWORD *)this + 4620) != 2
    && ((*((_DWORD *)this + 2433) & 0x400) != 0 || (*((_DWORD *)this + 2432) & 0x1000) != 0) )
  {
    if ( (g_DebugTraceComponent & 4) != 0 )
      _DbgPrintMessage(2, "Fast reconnect not supported on smartcard logon or always prompt for password");
    *((_DWORD *)this + 4620) = 0;
  }
  v108 = 30;
  v109 = 30;
  v110 = (char *)this + 9814;
  do
  {
    *v110++ = 0;
    --v109;
  }
  while ( v109 );
  v111 = 512;
  v112 = 512;
  v113 = v153;
  do
  {
    *(_BYTE *)v113 = 0;
    v113 = (unsigned __int16 *)((char *)v113 + 1);
    --v112;
  }
  while ( v112 );
  v114 = 512;
  Password = v155.Password;
  do
  {
    *(_BYTE *)Password = 0;
    Password = (WCHAR *)((char *)Password + 1);
    --v114;
  }
  while ( v114 );
  v116 = (char *)a2 + 124;
  do
  {
    *v116++ = 0;
    --v108;
  }
  while ( v108 );
  v117 = (char *)this + 14424;
  do
  {
    *v117++ = 0;
    --v111;
  }
  while ( v111 );
  if ( v135 )
    TSCompatShim::FreeMemoryUsingMSVCRT(v135, 0);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v137);
  wil::details::unique_storage_wil::details::resource_policy__WTS_SERIALIZED_USER_CREDENTIAL___void____cdecl____WTS_SERIALIZED_USER_CREDENTIAL_____WTSFreeSerializedUserCredential_wistd::integral_constant_unsigned___int64_0___WTS_SERIALIZED_USER_CREDENTIAL____WTS_SERIALIZED_USER_CREDENTIAL___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy__WTS_SERIALIZED_USER_CREDENTIAL___void____cdecl____WTS_SERIALIZED_USER_CREDENTIAL_____WTSFreeSerializedUserCredential_wistd::integral_constant_unsigned___int64_0___WTS_SERIALIZED_USER_CREDENTIAL____WTS_SERIALIZED_USER_CREDENTIAL___0_std::nullptr_t___(&pMemory);
  return (unsigned int)InstanceOfRemoteConnectionManager;
}

```

## disassembly

```asm
0x180080be0  push    rbp
0x180080be2  push    rbx
0x180080be3  push    rsi
0x180080be4  push    rdi
0x180080be5  push    r12
0x180080be7  push    r13
0x180080be9  push    r14
0x180080beb  push    r15
0x180080bed  lea     rbp, [rsp-1598h]
0x180080bf5  mov     eax, 1698h
0x180080bfa  call    _alloca_probe
0x180080bff  sub     rsp, rax
0x180080c02  mov     rax, cs:__security_cookie
0x180080c09  xor     rax, rsp
0x180080c0c  mov     [rbp+15D0h+var_50], rax
0x180080c13  mov     r12, r9
0x180080c16  mov     rbx, r8
0x180080c19  mov     r13, rdx
0x180080c1c  mov     rdi, rcx
0x180080c1f  mov     rax, [rbp+15D0h+arg_20]
0x180080c26  mov     [rbp+15D0h+var_15E8], rax
0x180080c2a  xor     edx, edx; Val
0x180080c2c  mov     r8d, 600h; Size
0x180080c32  lea     rcx, [rbp+15D0h+var_1510]; void *
0x180080c39  call    memset_0
0x180080c3e  xor     r14d, r14d
0x180080c41  mov     [rbp+15D0h+var_15F0], r14
0x180080c45  mov     [rbp+15D0h+var_1618], r14d
0x180080c49  mov     [rbp+15D0h+pMemory], r14
0x180080c4d  mov     [rbp+15D0h+var_1600], r14d
0x180080c51  xor     edx, edx; Val
0x180080c53  mov     r8d, 0E80h; Size
0x180080c59  lea     rcx, [rbp+15D0h+var_F10]; void *
0x180080c60  call    memset_0
0x180080c65  mov     [rbp+15D0h+var_15E0], r14
0x180080c69  lea     esi, [r14+1]
0x180080c6d  cmp     [rdi+648h], r14
0x180080c74  jz      short loc_180080CB5
0x180080c76  mov     eax, [rdi+45D8h]
0x180080c7c  sub     eax, 2
0x180080c7f  cmp     eax, esi
0x180080c81  ja      short loc_180080CB5
0x180080c83  xorps   xmm0, xmm0
0x180080c86  movups  [rbp+15D0h+Buf1], xmm0
0x180080c8a  lea     rdx, [rbp+15D0h+Buf1]; struct _GUID *
0x180080c8e  mov     rcx, rdi; this
0x180080c91  call    ?GetConnectionGUIDFromProtocol@CConnectionEx@@AEAAXPEAU_GUID@@@Z; CConnectionEx::GetConnectionGUIDFromProtocol(_GUID *)
0x180080c96  lea     r8d, [r14+10h]; Size
0x180080c9a  lea     rdx, TERMINAL_TYPE_RDP_REMOTEAPP; Buf2
0x180080ca1  lea     rcx, [rbp+15D0h+Buf1]; Buf1
0x180080ca5  call    memcmp_0
0x180080caa  test    eax, eax
0x180080cac  jnz     short loc_180080CB5
0x180080cae  or      dword ptr [rdi+2600h], 8
0x180080cb5  mov     r15d, [rdi+2600h]
0x180080cbc  mov     eax, r15d
0x180080cbf  shr     eax, 1Dh
0x180080cc2  and     al, sil
0x180080cc5  mov     [rbp+15D0h+var_F10.fDisableCpm], al
0x180080ccb  mov     eax, r15d
0x180080cce  shr     eax, 1Eh
0x180080cd1  and     al, sil
0x180080cd4  mov     [rbp+15D0h+var_F10.fDisableCdm], al
0x180080cda  mov     eax, r15d
0x180080cdd  shr     eax, 1Fh
0x180080ce0  mov     [rbp+15D0h+var_F10.fDisableCcm], al
0x180080ce6  mov     al, [rdi+2604h]
0x180080cec  and     al, sil
0x180080cef  mov     [rbp+15D0h+var_F10.fDisableLPT], al
0x180080cf5  mov     ecx, [rdi+2604h]
0x180080cfb  mov     eax, ecx
0x180080cfd  shr     eax, 1
0x180080cff  and     al, sil
0x180080d02  mov     [rbp+15D0h+var_F10.fDisableClip], al
0x180080d08  mov     eax, ecx
0x180080d0a  shr     eax, 0Bh
0x180080d0d  and     al, sil
0x180080d10  mov     [rbp+15D0h+var_F10.fDisablePNP], al
0x180080d16  mov     eax, r15d
0x180080d19  and     eax, esi
0x180080d1b  mov     [rbp+15D0h+var_F10.fInheritAutoLogon], eax
0x180080d21  mov     eax, r15d
0x180080d24  shr     eax, 3
0x180080d27  and     eax, esi
0x180080d29  mov     [rbp+15D0h+var_F10.fInheritInitialProgram], eax
0x180080d2f  shr     ecx, 8
0x180080d32  and     ecx, esi
0x180080d34  mov     [rbp+15D0h+var_F10.fInheritColorDepth], ecx
0x180080d3a  mov     rcx, [rdi+638h]
0x180080d41  mov     rax, [rcx]
0x180080d44  lea     rdx, [rbp+15D0h+var_F10]
0x180080d4b  mov     rax, [rax+28h]
0x180080d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080d54  mov     esi, eax
0x180080d56  test    eax, eax
0x180080d58  jns     short loc_180080DC6
0x180080d5a  mov     ecx, cs:dword_180128170
0x180080d60  cmp     ecx, 3
0x180080d63  jbe     loc_18008203A
0x180080d69  lea     rax, aInitializeclie; "InitializeClientData"
0x180080d70  mov     [rsp+16D0h+var_1658], rax
0x180080d75  lea     rax, aThisPtriwrdspr_2; "this->ptrIWRdsProtocolConnection->GetCl"...
0x180080d7c  lea     rdx, byte_18010F077
0x180080d83  mov     [rbp+15D0h+LsaHandle], rax
0x180080d87  lea     rax, aWarningHresult; "Warning HResult failed"
0x180080d8e  mov     [rbp+15D0h+var_1648], rax
0x180080d92  lea     rax, [rsp+16D0h+var_1658]
0x180080d97  mov     [rsp+16D0h+SourceContext], rax
0x180080d9c  lea     rax, [rsp+16D0h+var_1660]
0x180080da1  mov     [rsp+16D0h+var_1660], esi
0x180080da5  mov     [rsp+16D0h+LocalGroups], rax
0x180080daa  lea     rax, [rbp+15D0h+LsaHandle]
0x180080dae  mov     qword ptr [rsp+16D0h+AuthenticationInformationLength], rax
0x180080db3  lea     rax, [rbp+15D0h+var_1648]
0x180080db7  mov     [rsp+16D0h+AuthenticationInformation], rax
0x180080dbc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180080dc1  jmp     loc_18008203A
0x180080dc6  lea     rcx, [rbp+15D0h+var_15E0]; struct IRemoteConnectionManager **
0x180080dca  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x180080dcf  mov     esi, eax
0x180080dd1  test    eax, eax
0x180080dd3  jns     short loc_180080E00
0x180080dd5  mov     eax, cs:dword_180128170
0x180080ddb  cmp     eax, 3
0x180080dde  jbe     loc_18008203A
0x180080de4  lea     rax, aInitializeclie; "InitializeClientData"
0x180080deb  mov     [rsp+16D0h+var_1658], rax
0x180080df0  lea     rax, aGetinstanceofr_2; "GetInstanceOfRemoteConnectionManager"
0x180080df7  lea     rdx, qword_18010F038
0x180080dfe  jmp     short loc_180080D83
0x180080e00  mov     rcx, [rbp+15D0h+var_15E0]
0x180080e04  mov     rax, [rcx]
0x180080e07  mov     rax, [rax+190h]
0x180080e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080e13  test    eax, eax
0x180080e15  jz      short loc_180080E27
0x180080e17  mov     [rbp+15D0h+var_F10.DisplayDriverName], r14w
0x180080e1f  mov     [rbp+15D0h+var_F10.DisplayDeviceName], r14w
0x180080e27  mov     dword ptr [rdi+3EB8h], 1
0x180080e31  xor     edx, edx; Val
0x180080e33  mov     r8d, 468h; Size
0x180080e39  mov     rcx, rbx; void *
0x180080e3c  call    memset_0
0x180080e41  lea     r14, [rdi+2FF0h]
0x180080e48  lea     rdx, [rbp+15D0h+var_F10]; struct _WTS_CLIENT_DATA *
0x180080e4f  mov     rcx, r14; struct _WRDS_CONNECTION_SETTINGS *
0x180080e52  call    ?ConvertWTSClientDataToWRdsConnectionSetting@CHelper@@SAJPEAU_WRDS_CONNECTION_SETTINGS@@PEAU_WTS_CLIENT_DATA@@@Z; CHelper::ConvertWTSClientDataToWRdsConnectionSetting(_WRDS_CONNECTION_SETTINGS *,_WTS_CLIENT_DATA *)
0x180080e57  mov     esi, eax
0x180080e59  test    eax, eax
0x180080e5b  jns     short loc_180080E8B
0x180080e5d  mov     eax, cs:dword_180128170
0x180080e63  cmp     eax, 3
0x180080e66  jbe     loc_18008203A
0x180080e6c  lea     rax, aInitializeclie; "InitializeClientData"
0x180080e73  mov     [rsp+16D0h+var_1658], rax
0x180080e78  lea     rax, aChelperConvert_4; "CHelper::ConvertWTSClientDataToWRdsConn"...
0x180080e7f  lea     rdx, byte_18010EFF3
0x180080e86  jmp     loc_180080D83
0x180080e8b  mov     r8, r14; struct _WRDS_CONNECTION_SETTINGS *
0x180080e8e  mov     rdx, rbx; struct _WINSTATIONDOCONNECTMSG *
0x180080e91  mov     rcx, r13; struct _WINSTATIONCLIENTW *
0x180080e94  call    ?ConvertWRdsConnectionSettingToWinStationClient@CHelper@@SAJPEAU_WINSTATIONCLIENTW@@PEAU_WINSTATIONDOCONNECTMSG@@PEAU_WRDS_CONNECTION_SETTINGS@@@Z; CHelper::ConvertWRdsConnectionSettingToWinStationClient(_WINSTATIONCLIENTW *,_WINSTATIONDOCONNECTMSG *,_WRDS_CONNECTION_SETTINGS *)
0x180080e99  mov     esi, eax
0x180080e9b  xor     r14d, r14d
0x180080e9e  test    eax, eax
0x180080ea0  jns     short loc_180080ED0
0x180080ea2  mov     eax, cs:dword_180128170
0x180080ea8  cmp     eax, 3
0x180080eab  jbe     loc_18008203A
0x180080eb1  lea     rax, aInitializeclie; "InitializeClientData"
0x180080eb8  mov     [rsp+16D0h+var_1658], rax
0x180080ebd  lea     rax, aChelperConvert_3; "CHelper::ConvertWRdsConnectionSettingTo"...
0x180080ec4  lea     rdx, word_18010EFAE
0x180080ecb  jmp     loc_180080D83
0x180080ed0  shr     r15d, 0Ch
0x180080ed4  and     dword ptr [rdi+2600h], 0FFFFFFF6h
0x180080edb  mov     ecx, [rbp+15D0h+var_F10.fInheritInitialProgram]
0x180080ee1  mov     edx, 1
0x180080ee6  and     ecx, edx
0x180080ee8  shl     ecx, 3
0x180080eeb  mov     eax, [rbp+15D0h+var_F10.fInheritAutoLogon]
0x180080ef1  and     eax, edx
0x180080ef3  or      ecx, eax
0x180080ef5  or      [rdi+2600h], ecx
0x180080efb  btr     dword ptr [rdi+2604h], 8
0x180080f03  mov     eax, [rbp+15D0h+var_F10.fInheritColorDepth]
0x180080f09  and     eax, edx
0x180080f0b  shl     eax, 8
0x180080f0e  or      [rdi+2604h], eax
0x180080f14  mov     r8, rbx; struct _WINSTATIONDOCONNECTMSG *
0x180080f17  mov     rdx, r13; struct _WINSTATIONCLIENTW *
0x180080f1a  mov     rcx, rdi; this
0x180080f1d  call    ?MergeUserConfig@CConnectionEx@@AEAAJPEAU_WINSTATIONCLIENTW@@PEAU_WINSTATIONDOCONNECTMSG@@@Z; CConnectionEx::MergeUserConfig(_WINSTATIONCLIENTW *,_WINSTATIONDOCONNECTMSG *)
0x180080f22  mov     esi, eax
0x180080f24  test    eax, eax
0x180080f26  jns     short loc_180080F56
0x180080f28  mov     eax, cs:dword_180128170
0x180080f2e  cmp     eax, 3
0x180080f31  jbe     loc_18008203A
0x180080f37  lea     rax, aInitializeclie; "InitializeClientData"
0x180080f3e  mov     [rsp+16D0h+var_1658], rax
0x180080f43  lea     rax, aMergeuserconfi; "MergeUserConfig"
0x180080f4a  lea     rdx, byte_18010EF69
0x180080f51  jmp     loc_180080D83
0x180080f56  mov     eax, [rdi+2600h]
0x180080f5c  movzx   edx, [rbp+15D0h+var_F10.fDisableCpm]
0x180080f63  shl     edx, 1Dh
0x180080f66  xor     edx, eax
0x180080f68  and     edx, 20000000h
0x180080f6e  xor     edx, eax
0x180080f70  movzx   ecx, [rbp+15D0h+var_F10.fDisableCdm]
0x180080f77  shl     ecx, 1Eh
0x180080f7a  and     edx, 3FFFFFFFh
0x180080f80  xor     ecx, edx
0x180080f82  btr     ecx, 1Fh
0x180080f86  movzx   eax, [rbp+15D0h+var_F10.fDisableCcm]
0x180080f8d  shl     eax, 1Fh
0x180080f90  or      ecx, eax
0x180080f92  mov     [rdi+2600h], ecx
0x180080f98  mov     eax, [rdi+2604h]
0x180080f9e  movzx   ecx, [rbp+15D0h+var_F10.fDisableLPT]
0x180080fa5  xor     ecx, eax
0x180080fa7  mov     ebx, 1
0x180080fac  and     ecx, ebx
0x180080fae  xor     ecx, eax
0x180080fb0  movzx   edx, [rbp+15D0h+var_F10.fDisableClip]
0x180080fb7  add     edx, edx
0x180080fb9  xor     edx, ecx
0x180080fbb  and     edx, 2
0x180080fbe  xor     edx, ecx
0x180080fc0  movzx   eax, [rbp+15D0h+var_F10.fDisablePNP]
0x180080fc7  shl     eax, 0Bh
0x180080fca  xor     eax, edx
0x180080fcc  and     eax, 800h
0x180080fd1  xor     eax, edx
0x180080fd3  mov     [rdi+2604h], eax
0x180080fd9  mov     eax, cs:dword_180128170
0x180080fdf  cmp     eax, 4
0x180080fe2  jbe     short loc_18008101A
0x180080fe4  mov     rax, [rdi+648h]
0x180080feb  mov     [rsp+16D0h+var_1658], rax
0x180080ff0  lea     rax, aInitClientData; "Init client data0"
0x180080ff7  mov     [rbp+15D0h+LsaHandle], rax
0x180080ffb  lea     rax, [rsp+16D0h+var_1658]
0x180081000  mov     qword ptr [rsp+16D0h+AuthenticationInformationLength], rax
0x180081005  lea     rax, [rbp+15D0h+LsaHandle]
0x180081009  mov     [rsp+16D0h+AuthenticationInformation], rax
0x18008100e  lea     rdx, byte_18010EF2B
0x180081015  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18008101a  cmp     [rdi+648h], r14
0x180081021  jz      loc_180081388
0x180081027  xorps   xmm0, xmm0
0x18008102a  xor     eax, eax
0x18008102c  movups  xmmword ptr [rbp+15D0h+var_1540], xmm0
0x180081033  mov     qword ptr [rbp+15D0h+var_1540+10h], rax
0x18008103a  mov     rcx, [rdi+638h]
0x180081041  movups  xmm0, cs:PROPERTY_TYPE_GET_RESTRICTED_LOGON
0x180081048  movdqu  xmmword ptr [rbp+15D0h+var_1550.SourceName], xmm0
0x180081050  mov     rax, [rcx]
0x180081053  lea     rdx, [rbp+15D0h+var_1540]
0x18008105a  mov     qword ptr [rsp+16D0h+AuthenticationInformationLength], rdx
0x18008105f  mov     [rsp+16D0h+AuthenticationInformation], r14
0x180081064  mov     r9d, ebx
0x180081067  xor     r8d, r8d
0x18008106a  lea     rdx, [rbp+15D0h+var_1550]
0x180081071  mov     rax, [rax+0C0h]
0x180081078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008107d  mov     esi, eax
0x18008107f  test    eax, eax
0x180081081  jns     short loc_1800810B1
0x180081083  mov     eax, cs:dword_180128170
0x180081089  cmp     eax, 3
0x18008108c  jbe     loc_18008203A
0x180081092  lea     rax, aInitializeclie; "InitializeClientData"
0x180081099  mov     [rsp+16D0h+var_1658], rax
0x18008109e  lea     rax, aThisPtriwrdspr_12; "this->ptrIWRdsProtocolConnection->Query"...
0x1800810a5  lea     rdx, word_18010EEE6
0x1800810ac  jmp     loc_180080D83
0x1800810b1  mov     eax, dword ptr [rbp+15D0h+var_1540+8]
0x1800810b7  neg     eax
0x1800810b9  sbb     ecx, ecx
0x1800810bb  and     ecx, 1000h
0x1800810c1  btr     dword ptr [r13+0], 0Ch
0x1800810c7  or      [r13+0], ecx
0x1800810cb  mov     rcx, [rdi+638h]
0x1800810d2  movups  xmm0, cs:PROPERTY_TYPE_GET_REDIRECTED_AUTHENTICATION
0x1800810d9  movdqu  xmmword ptr [rbp+15D0h+var_1550.SourceName], xmm0
0x1800810e1  mov     rax, [rcx]
0x1800810e4  lea     rdx, [rbp+15D0h+var_1540]
0x1800810eb  mov     qword ptr [rsp+16D0h+AuthenticationInformationLength], rdx
0x1800810f0  mov     [rsp+16D0h+AuthenticationInformation], r14
0x1800810f5  mov     r9d, ebx
0x1800810f8  xor     r8d, r8d
0x1800810fb  lea     rdx, [rbp+15D0h+var_1550]
0x180081102  mov     rax, [rax+0C0h]
0x180081109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008110e  test    eax, eax
0x180081110  jns     short loc_18008111A
0x180081112  btr     dword ptr [r13+0], 0Dh
0x180081118  jmp     short loc_180081134
  ... truncated ...
```
