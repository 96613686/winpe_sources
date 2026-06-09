# CConnectionEx::InitializeClientData(_WINSTATIONCLIENTW *,_WINSTATIONDOCONNECTMSG *,int *,int *)

- ea: `0x1800843d0`
- end: `0x1800859a3`
- name: `?InitializeClientData@CConnectionEx@@UEAAJPEAU_WINSTATIONCLIENTW@@PEAU_WINSTATIONDOCONNECTMSG@@PEAH2@Z`
- size: `5587`
- prototype: `__int64 __fastcall(CConnectionEx *__hidden this, struct _WINSTATIONCLIENTW *, struct _WINSTATIONDOCONNECTMSG *, int *, int *)`
- caller_count: `0`
- callee_count: `46`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001294`
- `0x1800016a8`
- `0x180001f38`
- `0x1800020ec`
- `0x180002280`
- `0x180002328`
- `0x18000256c`
- `0x1800039a0`
- `0x180003a4c`
- `0x180003b90`
- `0x180009940`
- `0x18000c2a0`
- `0x1800139c0`
- `0x180014894`
- `0x180015310`
- `0x1800181dc`
- `0x180029ce4`
- `0x180029e48`
- `0x180029eac`
- `0x180033f60`
- `0x180034e64`
- `0x18006695c`
- `0x180066f5c`
- `0x18006775c`
- `0x1800678b4`
- `0x180067a58`
- `0x180067bd4`
- `0x180068cfc`
- `0x18007c974`
- `0x18007d070`
- `0x180081630`
- `0x1800816d0`
- `0x180081754`
- `0x180083274`
- `0x180083e90`
- `0x1800843d0`
- `0x180085e0c`
- `0x180087950`
- `0x180087ef0`
- `0x180088c0c`
- `0x180088c34`
- `0x1800898c8`
- `0x18008a5d4`
- `0x1800cae70`
- `0x1800caed0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084e04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800857e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084e04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800857e9`
- `SspiCli!LsaConnectUntrusted` at `0x1800851f3`
- `SspiCli!LsaConnectUntrusted` at `0x1800851f3`
- `SspiCli!LogonUserExExW` at `0x180084de8`
- `SspiCli!LogonUserExExW` at `0x1800856d7`
- `SspiCli!LogonUserExExW` at `0x1800857cd`
- `SspiCli!LogonUserExExW` at `0x180084de8`
- `SspiCli!LogonUserExExW` at `0x1800856d7`
- `SspiCli!LogonUserExExW` at `0x1800857cd`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180085557`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180085557`
- `SspiCli!LsaLogonUser` at `0x18008542d`
- `SspiCli!LsaLogonUser` at `0x18008542d`
- `WTSAPI32!WTSFreeMemoryExW` at `0x180084f15`
- `WTSAPI32!WTSFreeMemoryExW` at `0x180084f15`

## string_xrefs

- `0x180084565`: `this->ptrIWRdsProtocolConnection->GetClientData`
- `0x180084733`: `MergeUserConfig`
- `0x18008488e`: `this->ptrIWRdsProtocolConnection->QueryProperty(PROPERTY_TYPE_RESTRICTED_LOGON)`
- `0x180085141`: `Terminal Services API`
- `0x18008531e`: `FastReconnectAADTipTest::reason::GetSecurityFilterClientTokenFailed`
- `0x180085479`: `FastReconnectAADTipTest::reason::GetSecurityFilterClientTokenFailed`
- `0x18008534a`: `CConnectionEx::GetSecurityFilterClientToken failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  const char *v13; // r9
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
  __int64 v42; // rax
  DWORD LastError; // eax
  __int64 v44; // rcx
  struct _QUOTA_LIMITS *v45; // rax
  int (__fastcall ***v46)(_QWORD, GUID *, __int64 *); // rcx
  int (__fastcall **v47)(_QWORD, GUID *, __int64 *); // rax
  __int64 v48; // rsi
  int (__fastcall *v49)(__int64, PVOID *); // r14
  PVOID v50; // rbx
  int v51; // r9d
  __int64 v52; // rcx
  _QWORD *v53; // r14
  int InstanceOfSecFilterCredentials; // eax
  int v55; // r8d
  int v56; // r9d
  __int64 v57; // rcx
  int *v58; // rbx
  int v59; // eax
  __int64 v60; // rbx
  int v61; // ecx
  int v62; // r8d
  int v63; // r9d
  PVOID AuthenticationInformation; // r15
  const char *v65; // rdx
  NTSTATUS v66; // r14d
  const char *v67; // rax
  int v68; // r8d
  int v69; // r9d
  int InstanceOfWtsSerializedUserCredentials; // eax
  const char *v71; // rdx
  const char *v72; // rax
  int v73; // ecx
  int v74; // r8d
  int v75; // r9d
  NTSTATUS v76; // eax
  int v77; // ecx
  __int64 v78; // r8
  int v79; // r9d
  const char *v80; // rdx
  const char *v81; // rax
  int v82; // eax
  int v83; // ecx
  int v84; // r8d
  int v85; // r9d
  __int64 v86; // rax
  _BYTE *v87; // rcx
  int v88; // eax
  int v89; // ecx
  unsigned __int16 *v90; // rcx
  int InstanceOfSmartCardCredentials; // eax
  unsigned __int16 *v92; // r8
  int InstanceOfPasswordCredentials; // eax
  __int64 v94; // rax
  int v95; // eax
  const unsigned __int16 *v96; // r8
  __int64 v97; // rax
  DWORD v98; // eax
  __int64 v99; // rcx
  int v100; // eax
  int v101; // r8d
  __int64 v102; // rdx
  __int64 v103; // rcx
  char *v104; // rax
  __int64 v105; // rax
  __int64 v106; // r8
  unsigned __int16 *v107; // rcx
  __int64 v108; // r8
  WCHAR *Password; // rcx
  char *v110; // rcx
  char *v111; // rdi
  int v113; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v114[4]; // [rsp+74h] [rbp-8Ch] BYREF
  void *Token; // [rsp+78h] [rbp-88h] BYREF
  int v116; // [rsp+80h] [rbp-80h] BYREF
  const char *v117; // [rsp+88h] [rbp-78h] BYREF
  void *LsaHandle; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v119[8]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v120; // [rsp+A0h] [rbp-60h] BYREF
  const char *v121; // [rsp+A8h] [rbp-58h] BYREF
  const char *v122; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v123; // [rsp+B8h] [rbp-48h] BYREF
  int SubStatus; // [rsp+BCh] [rbp-44h] BYREF
  ULONG ProfileBufferLength; // [rsp+C0h] [rbp-40h] BYREF
  PVOID pMemory; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v127; // [rsp+D0h] [rbp-30h] BYREF
  const char *v128; // [rsp+D8h] [rbp-28h] BYREF
  TSCompatShim *v129; // [rsp+E0h] [rbp-20h] BYREF
  int *v130; // [rsp+E8h] [rbp-18h]
  struct IRemoteConnectionManager *v131; // [rsp+F0h] [rbp-10h] BYREF
  const char *v132; // [rsp+F8h] [rbp-8h] BYREF
  const char *v133; // [rsp+100h] [rbp+0h] BYREF
  PVOID ProfileBuffer; // [rsp+108h] [rbp+8h] BYREF
  struct _GUID Buf1; // [rsp+110h] [rbp+10h] BYREF
  ULONG AuthenticationInformationLength[2]; // [rsp+120h] [rbp+20h] BYREF
  PVOID v137; // [rsp+128h] [rbp+28h]
  __int64 v138; // [rsp+130h] [rbp+30h]
  struct _LUID LogonId; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v140[56]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v141; // [rsp+178h] [rbp+78h]
  struct _TOKEN_SOURCE SourceContext; // [rsp+180h] [rbp+80h] BYREF
  _DWORD v143[6]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v144; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v145; // [rsp+1B8h] [rbp+B8h]
  unsigned __int16 v146[256]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 v147[256]; // [rsp+3C0h] [rbp+2C0h] BYREF
  unsigned __int16 v148[256]; // [rsp+5C0h] [rbp+4C0h] BYREF
  struct _WTS_CLIENT_DATA v149; // [rsp+7C0h] [rbp+6C0h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+1640h] [rbp+1540h] BYREF

  v130 = a5;
  memset_0(v146, 0, 0x600u);
  v129 = 0;
  v123 = 0;
  pMemory = 0;
  v127 = 0;
  memset_0(&v149, 0, sizeof(v149));
  v131 = 0;
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
  v149.fDisableCpm = (v9 & 0x20000000) != 0;
  v149.fDisableCdm = (v9 & 0x40000000) != 0;
  v149.fDisableCcm = v9 < 0;
  v149.fDisableLPT = *((_BYTE *)this + 9732) & 1;
  v10 = *((_DWORD *)this + 2433);
  v149.fDisableClip = (v10 & 2) != 0;
  v149.fDisablePNP = (v10 & 0x800) != 0;
  v149.fInheritAutoLogon = v9 & 1;
  v149.fInheritInitialProgram = ((unsigned int)v9 >> 3) & 1;
  v149.fInheritColorDepth = (v10 >> 8) & 1;
  InstanceOfRemoteConnectionManager = (*(__int64 (__fastcall **)(_QWORD, struct _WTS_CLIENT_DATA *))(**((_QWORD **)this + 199) + 40LL))(
                                        *((_QWORD *)this + 199),
                                        &v149);
  if ( InstanceOfRemoteConnectionManager >= 0 )
  {
    InstanceOfRemoteConnectionManager = GetInstanceOfRemoteConnectionManager(&v131);
    if ( InstanceOfRemoteConnectionManager < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_182;
      Token = "InitializeClientData";
      v15 = "GetInstanceOfRemoteConnectionManager";
      v16 = (char *)qword_1801150B8;
      goto LABEL_8;
    }
    if ( (*(unsigned int (__fastcall **)(struct IRemoteConnectionManager *))(*(_QWORD *)v131 + 400LL))(v131) )
    {
      v149.DisplayDriverName[0] = 0;
      v149.DisplayDeviceName[0] = 0;
    }
    *((_DWORD *)this + 4014) = 1;
    memset_0(a3, 0, 0x468u);
    InstanceOfRemoteConnectionManager = CHelper::ConvertWTSClientDataToWRdsConnectionSetting(
                                          (struct _WRDS_CONNECTION_SETTINGS *)((char *)this + 12272),
                                          &v149);
    if ( InstanceOfRemoteConnectionManager < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_182;
      Token = "InitializeClientData";
      v15 = "CHelper::ConvertWTSClientDataToWRdsConnectionSetting";
      v16 = byte_180115073;
      goto LABEL_8;
    }
    InstanceOfRemoteConnectionManager = CHelper::ConvertWRdsConnectionSettingToWinStationClient(
                                          a2,
                                          a3,
                                          (struct _WRDS_CONNECTION_SETTINGS *)((char *)this + 12272));
    if ( InstanceOfRemoteConnectionManager < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_182;
      Token = "InitializeClientData";
      v15 = "CHelper::ConvertWRdsConnectionSettingToWinStationClient";
      v16 = (char *)&word_18011502E;
      goto LABEL_8;
    }
    v17 = (unsigned int)v9 >> 12;
    *((_DWORD *)this + 2432) &= 0xFFFFFFF6;
    *((_DWORD *)this + 2432) |= v149.fInheritAutoLogon & 1 | (8 * (v149.fInheritInitialProgram & 1));
    *((_DWORD *)this + 2433) &= ~0x100u;
    *((_DWORD *)this + 2433) |= (v149.fInheritColorDepth & 1) << 8;
    InstanceOfRemoteConnectionManager = CConnectionEx::MergeUserConfig(this, a2, a3);
    if ( InstanceOfRemoteConnectionManager < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_182;
      Token = "InitializeClientData";
      v15 = "MergeUserConfig";
      v16 = byte_180114FE9;
      goto LABEL_8;
    }
    *((_DWORD *)this + 2432) = (v149.fDisableCcm << 31)
                             | ((*((_DWORD *)this + 2432)
                               ^ (*((_DWORD *)this + 2432)
                                ^ (v149.fDisableCpm << 29))
                               & 0x20000000)
                              & 0x3FFFFFFF
                              ^ (v149.fDisableCdm << 30))
                             & 0x7FFFFFFF;
    v18 = *((_DWORD *)this + 2433) ^ (*((_DWORD *)this + 2433) ^ v149.fDisableLPT) & 1;
    *((_DWORD *)this + 2433) = v18
                             ^ (*((_BYTE *)this + 9732)
                              ^ (*((_BYTE *)this + 9732)
                               ^ v149.fDisableLPT)
                              & 1
                              ^ (unsigned __int8)(2 * v149.fDisableClip))
                             & 2
                             ^ (*((_WORD *)this + 4866)
                              ^ (*((_WORD *)this + 4866)
                               ^ v149.fDisableLPT)
                              & 1
                              ^ (*((_BYTE *)this + 9732)
                               ^ (*((_BYTE *)this + 9732)
                                ^ v149.fDisableLPT)
                               & 1
                               ^ (unsigned __int8)(2 * v149.fDisableClip))
                              & 2
                              ^ (unsigned __int16)(v149.fDisablePNP << 11))
                             & 0x800;
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      Token = (void *)*((_QWORD *)this + 201);
      LsaHandle = "Init client data0";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v18,
        (unsigned int)byte_180114FAB,
        v12,
        (_DWORD)v13,
        (__int64)&LsaHandle,
        (__int64)&Token);
    }
    if ( *((_QWORD *)this + 201) )
    {
      memset(v143, 0, sizeof(v143));
      v19 = *((_QWORD *)this + 199);
      SourceContext = (struct _TOKEN_SOURCE)PROPERTY_TYPE_GET_RESTRICTED_LOGON;
      InstanceOfRemoteConnectionManager = (*(__int64 (__fastcall **)(__int64, struct _TOKEN_SOURCE *, _QWORD, __int64, _QWORD, _DWORD *))(*(_QWORD *)v19 + 192LL))(
                                            v19,
                                            &SourceContext,
                                            0,
                                            1,
                                            0,
                                            v143);
      if ( InstanceOfRemoteConnectionManager < 0 )
      {
        if ( (unsigned int)dword_18012E170 <= 3 )
          goto LABEL_182;
        Token = "InitializeClientData";
        v15 = "this->ptrIWRdsProtocolConnection->QueryProperty(PROPERTY_TYPE_RESTRICTED_LOGON)";
        v16 = (char *)&word_180114F66;
        goto LABEL_8;
      }
      v20 = v143[2] != 0 ? 0x1000 : 0;
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
             v143) >= 0 )
      {
        v22 = v143[2] != 0 ? 0x2000 : 0;
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
              v143);
      if ( v24 >= 0 )
      {
        if ( (unsigned __int8)(LOBYTE(v143[2]) - 5) > 0xF9u )
        {
          *((_BYTE *)this + 18624) = v143[2];
        }
        else if ( (unsigned int)dword_18012E170 > 2 )
        {
          v114[0] = v143[2];
          Token = "The stack SC ClipLevel is out-of-range, reset to use default value";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>>(
            v143[2],
            (unsigned int)byte_180114EF9,
            v25,
            v26,
            (__int64)&Token,
            (__int64)v114);
        }
      }
      else if ( (unsigned int)dword_18012E170 > 3 )
      {
        v113 = v24;
        Token = "Failed to query stack SC ClipLevel, non-fatal";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_18012E170,
          (unsigned int)&word_180114F36,
          v25,
          v26,
          (__int64)&Token,
          (__int64)&v113);
      }
      v27 = *((_QWORD *)this + 199);
      SourceContext = (struct _TOKEN_SOURCE)PROPERTY_TYPE_GET_STACK_CS_CLIP_LEVEL;
      v28 = (*(__int64 (__fastcall **)(__int64, struct _TOKEN_SOURCE *, _QWORD, __int64, _QWORD, _DWORD *))(*(_QWORD *)v27 + 192LL))(
              v27,
              &SourceContext,
              0,
              1,
              0,
              v143);
      if ( v28 >= 0 )
      {
        v31 = v143[2];
        if ( (unsigned __int8)(LOBYTE(v143[2]) - 5) > 0xF9u )
        {
          *((_BYTE *)this + 18625) = v143[2];
        }
        else if ( (unsigned int)dword_18012E170 > 2 )
        {
          v114[0] = v143[2];
          Token = "The stack CS ClipLevel is out-of-range, reset to use default value";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>>(
            v143[2],
            (unsigned int)&dword_180114E8C,
            v29,
            v30,
            (__int64)&Token,
            (__int64)v114);
        }
      }
      else
      {
        v31 = dword_18012E170;
        if ( (unsigned int)dword_18012E170 > 3 )
        {
          v113 = v28;
          Token = "Failed to query stack CS ClipLevel, non-fatal";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            dword_18012E170,
            (unsigned int)byte_180114EC9,
            v29,
            v30,
            (__int64)&Token,
            (__int64)&v113);
        }
      }
      if ( (unsigned int)dword_18012E170 > 4 )
      {
        v114[0] = *((_BYTE *)this + 18625);
        v119[0] = *((_BYTE *)this + 18624);
        Token = "Got stack clipboard levels";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
          v31,
          (unsigned int)byte_180114E43,
          v29,
          v30,
          (__int64)&Token,
          (__int64)v119,
          (__int64)v114);
      }
      if ( *((_QWORD *)this + 201) )
      {
        if ( (unsigned int)dword_18012E170 > 5 )
        {
          Token = "Microsoft RDP Stack detected, assuming Basic Fast Reconnect by default";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v31,
            (unsigned int)qword_180114E20,
            v29,
            v30,
            (__int64)&Token);
        }
        *((_DWORD *)this + 4620) = 1;
      }
    }
    v144 = 0;
    v145 = 0;
    v32 = *((_QWORD *)this + 199);
    SourceContext = (struct _TOKEN_SOURCE)PROPERTY_TYPE_GET_FAST_RECONNECT;
    v33 = (*(__int64 (__fastcall **)(__int64, struct _TOKEN_SOURCE *, _QWORD, __int64, _QWORD, __int128 *))(*(_QWORD *)v32 + 192LL))(
            v32,
            &SourceContext,
            0,
            1,
            0,
            &v144);
    if ( v33 >= 0 )
    {
      if ( (_WORD)v144 == 1 )
      {
        if ( DWORD2(v144) )
        {
          if ( DWORD2(v144) == 1 )
          {
            *((_DWORD *)this + 4620) = 1;
          }
          else if ( DWORD2(v144) == 2 )
          {
            *((_DWORD *)this + 4620) = 2;
          }
          else if ( (unsigned int)dword_18012E170 > 2 )
          {
            v113 = *((_DWORD *)this + 4620);
            v116 = DWORD2(v144);
            Token = "Unsupported Fast Reconnect type returned by stack. Default value set";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v34,
              (unsigned int)&word_180114DB6,
              v35,
              v36,
              (__int64)&Token,
              (__int64)&v116,
              (__int64)&v113);
          }
        }
        else
        {
          *((_DWORD *)this + 4620) = 0;
        }
        if ( (unsigned int)dword_18012E170 > 5 )
        {
          v116 = *((_DWORD *)this + 4620);
          v113 = DWORD2(v144);
          Token = "Setting eFastReconnectType from stack";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v34,
            (unsigned int)&dword_180114D74,
            v35,
            v36,
            (__int64)&Token,
            (__int64)&v113,
            (__int64)&v116);
        }
      }
      else if ( (unsigned int)dword_18012E170 > 2 )
      {
        Token = "Fast Reconnect property from stack wasn't a ULONG";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v34,
          (unsigned int)byte_180114D51,
          v35,
          v36,
          (__int64)&Token);
      }
    }
    else if ( (unsigned int)dword_18012E170 > 3 )
    {
      v113 = v33;
      Token = "Failed to query fast reconnect property";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_18012E170,
        (unsigned int)qword_180114DF8,
        v35,
        v36,
        (__int64)&Token,
        (__int64)&v113);
    }
    v37 = *((_DWORD *)this + 2432);
    if ( (v37 & 1) == 0 )
    {
      v38 = 0;
      if ( (v37 & 0x1000) == 0 )
      {
        v39 = CAutologonPassword::Retrieve((unsigned __int16 *const)&Quotas, (const unsigned __int16 *)this + 848);
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
      v42 = -1;
      do
        ++v42;
      while ( v38[v42] );
      if ( v42 )
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
          v44 = 64;
          v45 = &Quotas;
          do
          {
            LOBYTE(v45->PagedPoolLimit) = 0;
            v45 = (struct _QUOTA_LIMITS *)((char *)v45 + 1);
            --v44;
          }
          while ( v44 );
          if ( InstanceOfRemoteConnectionManager < 0 && (unsigned int)dword_18012E170 > 3 )
          {
            Token = "InitializeClientData";
            v116 = InstanceOfRemoteConnectionManager;
            LsaHandle = "GetInstanceOfPasswordCredentials";
            v117 = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              0,
              (unsigned int)&dword_180114D0C,
              v41,
              (_DWORD)v13,
              (__int64)&v117,
              (__int64)&LsaHandle,
              (__int64)&v116,
              (__int64)&Token);
          }
          goto LABEL_182;
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
    v120 = 0;
    v46 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 199);
    v47 = *v46;
    v120 = 0;
    if ( (*v47)(v46, &GUID_c2bd9b66_4a76_4701_b6a3_bfafc1482169, &v120) >= 0 )
    {
      v48 = v120;
      v49 = *(int (__fastcall **)(__int64, PVOID *))(*(_QWORD *)v120 + 216LL);
      v50 = pMemory;
      if ( pMemory )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&Token);
        WTSFreeMemoryExW((WTS_TYPE_CLASS)4, v50, 1u);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&Token);
      }
      pMemory = 0;
      if ( v49(v48, &pMemory) >= 0 )
        goto LABEL_96;
    }
    v52 = *((_QWORD *)this + 201);
    if ( v52 )
    {
      if ( (*(int (__fastcall **)(__int64, TSCompatShim **, unsigned int *, unsigned int *))(*(_QWORD *)v52 + 32LL))(
             v52,
             &v129,
             &v123,
             &v127) >= 0 )
      {
LABEL_96:
        if ( v123 || pMemory )
        {
          if ( (v17 & 1) != 0 && (*(_DWORD *)a2 & 0x800) != 0 )
          {
            CConnectionEx::SetErrorInfo(this, 0xAu, 0);
            InstanceOfRemoteConnectionManager = -2147024891;
            _DbgPrintMessage(8, "Disconnecting because fresh credential is required");
LABEL_181:
            SmartPtr<IWRdsWddmIddProps1>::~SmartPtr<IWRdsWddmIddProps1>(&v120);
            goto LABEL_182;
          }
          if ( v123 )
          {
            v53 = (_QWORD *)((char *)this + 16040);
            InstanceOfSecFilterCredentials = CCredentialsFactory::GetInstanceOfSecFilterCredentials(
                                               (unsigned __int8 *)v129,
                                               v123,
                                               v127,
                                               v51,
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
              goto LABEL_181;
            }
            v129 = 0;
            v123 = 0;
          }
          else
          {
            if ( !pMemory )
            {
              InstanceOfRemoteConnectionManager = -2147418113;
              _DbgPrintMessage(8, "Unexpected credentials buffer!");
              goto LABEL_181;
            }
            v53 = (_QWORD *)((char *)this + 16040);
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
              goto LABEL_181;
            }
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FastReconnectWithAADCreds>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FastReconnectWithAADCreds>::GetImpl'::`2'::impl) )
          {
            v57 = *v53;
            v58 = v130;
            if ( *v53 )
            {
              v59 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v57 + 40LL))(v57, a4, v130);
              LODWORD(v57) = dword_18012E170;
              if ( (unsigned int)dword_18012E170 > 5 )
              {
                v116 = InstanceOfRemoteConnectionManager;
                v113 = v59;
                LODWORD(v121) = *a4;
                Token = "GetDisconnectOnLockPolicy returned";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  dword_18012E170,
                  (unsigned int)&unk_180114CB8,
                  v55,
                  v56,
                  (__int64)&Token,
                  (__int64)&v121,
                  (__int64)&v113,
                  (__int64)&v116);
              }
            }
            if ( (unsigned int)dword_18012E170 > 5 )
            {
              Token = "Feature_FastReconnectWithAADCreds is enabled";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                v57,
                (unsigned int)byte_180114C95,
                v55,
                v56,
                (__int64)&Token);
            }
            if ( *v58 )
            {
              v117 = 0;
              tip2::tip_test<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>>::start_and_watch_errors(
                &v117,
                v140);
              wil::com_ptr_t<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>,wil::err_returncode_policy>(&v117);
              v60 = v141;
              v117 = (const char *)v141;
              if ( v141 )
                _InterlockedIncrement((volatile signed __int32 *)(v141 + 272));
              tip2::test_watcher<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>>::~test_watcher<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>>(v140);
              if ( (unsigned int)dword_18012E170 > 5 )
              {
                v121 = "Using AAD creds, going to try to use fast reconnect";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  v61,
                  (unsigned int)word_180114C72,
                  v62,
                  v63,
                  (__int64)&v121);
              }
              strcpy((char *)v143, "Terminal Services API");
              *(_QWORD *)&Buf1.Data1 = 1441814;
              *(_QWORD *)Buf1.Data4 = v143;
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
              v137 = 0;
              v138 = 0;
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v53 + 48LL))(*v53);
              (*(void (__fastcall **)(_QWORD, ULONG *))(*(_QWORD *)*v53 + 24LL))(*v53, AuthenticationInformationLength);
              AuthenticationInformation = v137;
              v66 = LsaConnectUntrusted(&LsaHandle);
              if ( v66 < 0 )
              {
                v67 = tip2::details::reason_string(
                        (tip2::details *)"FastReconnectAADTipTest::reason::LsaConnectUntrustedFailed",
                        v65);
                tip2::tip_test<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>>::complete_and_fail(
                  &v117,
                  0,
                  v67);
                InstanceOfRemoteConnectionManager = -2147467259;
                if ( (unsigned int)dword_18012E170 > 2 )
                {
                  LODWORD(v121) = v66;
                  v132 = "LsaConnectUntrusted failed";
                  v133 = "InitializeClientData";
                  v116 = 1381;
                  v128 = "clientcore\\termsrv\\newsvc\\remote\\extcon.cpp";
                  v113 = -2147467259;
                  v122 = "Error HResult failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                    dword_18012E170,
                    (unsigned int)qword_180114C18,
                    v68,
                    v69,
                    (__int64)&v122,
                    (__int64)&v113,
                    (__int64)&v128,
                    (__int64)&v116,
                    (__int64)&v133,
                    (__int64)&v132,
                    (__int64)&v121);
                }
LABEL_118:
                wil::com_ptr_t<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>,wil::err_returncode_policy>(&v117);
                goto LABEL_181;
              }
              InstanceOfRemoteConnectionManager = CConnectionEx::GetSecurityFilterClientToken(this, 0, &Token);
              if ( InstanceOfRemoteConnectionManager < 0 )
              {
                v72 = tip2::details::reason_string(
                        (tip2::details *)"FastReconnectAADTipTest::reason::GetSecurityFilterClientTokenFailed",
                        v71);
                tip2::tip_test<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>>::complete_and_fail(
                  &v117,
                  1,
                  v72);
                if ( (unsigned int)dword_18012E170 > 2 )
                {
                  v122 = "CConnectionEx::GetSecurityFilterClientToken failed";
                  v128 = "InitializeClientData";
                  LODWORD(v121) = 1387;
                  v133 = "clientcore\\termsrv\\newsvc\\remote\\extcon.cpp";
                  v116 = InstanceOfRemoteConnectionManager;
                  v132 = "Error HResult failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    v73,
                    (unsigned int)byte_180114BC9,
                    v74,
                    v75,
                    (__int64)&v132,
                    (__int64)&v116,
                    (__int64)&v133,
                    (__int64)&v121,
                    (__int64)&v128,
                    (__int64)&v122);
                }
                goto LABEL_118;
              }
              v76 = LsaLogonUser(
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
              v80 = (const char *)(unsigned int)v76;
              if ( v76 >= 0 )
              {
                InstanceOfRemoteConnectionManager = 0;
                if ( (unsigned int)dword_18012E170 > 4 )
                {
                  LODWORD(v121) = v76;
                  v116 = 0;
                  v122 = "LsaLogonuser succeeded, setting fast reconnect type to basic";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                    v77,
                    (unsigned int)qword_180114B68,
                    v78,
                    v79,
                    (__int64)&v122,
                    (__int64)&v116,
                    (__int64)&v121);
                }
                if ( (unsigned int)dword_18012E170 > 5
                  && (unsigned __int8)tlgKeywordOn(&dword_18012E170, 0x400000000000LL, v78) )
                {
                  v122 = "LsaLogonUser succeeded with AAD creds";
                  v128 = (const char *)0x2000000;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
                    v83,
                    (unsigned int)word_180114B2A,
                    v84,
                    v85,
                    (__int64)&v128,
                    (__int64)&v122);
                }
                v82 = 1;
              }
              else
              {
                if ( (unsigned int)dword_18012E170 > 2 )
                {
                  LODWORD(v121) = v76;
                  v122 = "LsaLogonUser failed, set EFastReconnectType to None";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                    dword_18012E170,
                    (unsigned int)byte_180114B9B,
                    v78,
                    v79,
                    (__int64)&v122,
                    (__int64)&v121);
                }
                v81 = tip2::details::reason_string(
                        (tip2::details *)"FastReconnectAADTipTest::reason::GetSecurityFilterClientTokenFailed",
                        v80);
                tip2::tip_test<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>>::complete_and_fail(
                  &v117,
                  1,
                  v81);
                v82 = 0;
              }
              *((_DWORD *)this + 4620) = v82;
              if ( LsaHandle )
                LsaDeregisterLogonProcess(LsaHandle);
              v86 = AuthenticationInformationLength[1];
              v87 = v137;
              if ( AuthenticationInformationLength[1] )
              {
                do
                {
                  *v87++ = 0;
                  --v86;
                }
                while ( v86 );
              }
              if ( v60 )
              {
                wil::EnterCriticalSection(&v122, v60 + 200);
                tip2::details::shared_data<0,0,0>::complete_helper(v60 + 8);
                wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v122);
              }
              wil::com_ptr_t<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FastReconnectAADTipTest,_tip_FastReconnectAADTipTest>,wil::err_returncode_policy>(&v117);
            }
          }
          *((_DWORD *)this + 4332) = 1;
          goto LABEL_181;
        }
      }
    }
    v88 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 199) + 56LL))(
            *((_QWORD *)this + 199),
            v146);
    v89 = *((_DWORD *)this + 2432) & 0x1000;
    if ( v88 < 0 )
    {
      if ( !v89 && (*((_DWORD *)this + 2433) & 0x400) != 0 )
      {
        v90 = (unsigned __int16 *)((char *)this + 9814);
LABEL_148:
        InstanceOfSmartCardCredentials = CCredentialsFactory::GetInstanceOfSmartCardCredentials(
                                           v90,
                                           (struct ICredentials **)this + 2005);
        InstanceOfRemoteConnectionManager = InstanceOfSmartCardCredentials;
        if ( InstanceOfSmartCardCredentials < 0 )
          _DbgPrintMessage(
            8,
            "GetInstanceOfSmartCardCredentials failed: 0x%x in %s",
            (unsigned int)InstanceOfSmartCardCredentials,
            "CConnectionEx::InitializeClientData");
        goto LABEL_181;
      }
      if ( v89 )
        v96 = 0;
      else
        v96 = (const unsigned __int16 *)((char *)this + 9814);
      InstanceOfPasswordCredentials = CCredentialsFactory::GetInstanceOfPasswordCredentials(
                                        (const unsigned __int16 *)this + 4868,
                                        (const unsigned __int16 *)this + 4889,
                                        v96,
                                        (struct ICredentials **)this + 2005);
      InstanceOfRemoteConnectionManager = InstanceOfPasswordCredentials;
      if ( InstanceOfPasswordCredentials < 0 )
      {
LABEL_153:
        _DbgPrintMessage(
          8,
          "GetInstanceOfPasswordCredentials failed: 0x%x in %s",
          (unsigned int)InstanceOfPasswordCredentials,
          "CConnectionEx::InitializeClientData");
        goto LABEL_181;
      }
      if ( *((_DWORD *)this + 4620) != 1 )
        goto LABEL_181;
      if ( this == (CConnectionEx *)-9814LL )
        goto LABEL_178;
      v97 = -1;
      do
        ++v97;
      while ( *((_WORD *)this + v97 + 4907) );
      if ( !v97 )
      {
LABEL_178:
        if ( (g_DebugTraceComponent & 4) != 0 )
          _DbgPrintMessage(2, "Password length is zero, disabling fast reconnect");
        *((_DWORD *)this + 4620) = 0;
        goto LABEL_181;
      }
      v95 = LogonUserExExW(
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
      if ( !v89 && (*((_DWORD *)this + 2433) & 0x400) != 0 )
      {
        v90 = v147;
        goto LABEL_148;
      }
      v92 = v147;
      if ( v89 )
        v92 = 0;
      InstanceOfPasswordCredentials = CCredentialsFactory::GetInstanceOfPasswordCredentials(
                                        v146,
                                        v148,
                                        v92,
                                        (struct ICredentials **)this + 2005);
      InstanceOfRemoteConnectionManager = InstanceOfPasswordCredentials;
      if ( InstanceOfPasswordCredentials < 0 )
        goto LABEL_153;
      if ( *((_DWORD *)this + 4620) != 1 )
        goto LABEL_181;
      v94 = -1;
      do
        ++v94;
      while ( v147[v94] );
      if ( !v94 )
      {
        if ( (g_DebugTraceComponent & 4) != 0 )
          _DbgPrintMessage(2, "Password length is zero, disabling fast reconnect");
        goto LABEL_177;
      }
      v95 = LogonUserExExW(v146, v148, v147, 3, 0, 0, (char *)this + 17952, 0, 0, 0, 0);
    }
    if ( v95 )
      goto LABEL_181;
    if ( (g_DebugTraceComponent & 4) != 0 )
    {
      v98 = GetLastError();
      _DbgPrintMessage(2, "Failed to logon using clear text 2, error code 0x%08x", v98);
    }
LABEL_177:
    *((_DWORD *)this + 4620) = 0;
    goto LABEL_181;
  }
  v14 = dword_18012E170;
  if ( (unsigned int)dword_18012E170 > 3 )
  {
    Token = "InitializeClientData";
    v15 = "this->ptrIWRdsProtocolConnection->GetClientData";
    v16 = &byte_1801150F7;
LABEL_8:
    LsaHandle = v15;
    v117 = "Warning HResult failed";
    v113 = InstanceOfRemoteConnectionManager;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v14,
      (_DWORD)v16,
      v12,
      (_DWORD)v13,
      (__int64)&v117,
      (__int64)&LsaHandle,
      (__int64)&v113,
      (__int64)&Token);
  }
LABEL_182:
  v99 = *((_QWORD *)this + 2005);
  if ( v99 )
  {
    v100 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v99 + 40LL))(v99, a4, v130);
    if ( (unsigned int)dword_18012E170 > 5 )
    {
      ProfileBufferLength = InstanceOfRemoteConnectionManager;
      SubStatus = v100;
      LODWORD(v121) = *a4;
      ProfileBuffer = "GetDisconnectOnLockPolicy returned";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        dword_18012E170,
        (unsigned int)&word_180114AD6,
        v101,
        (_DWORD)v13,
        (__int64)&ProfileBuffer,
        (__int64)&v121,
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
  v102 = 30;
  v103 = 30;
  v104 = (char *)this + 9814;
  do
  {
    *v104++ = 0;
    --v103;
  }
  while ( v103 );
  v105 = 512;
  v106 = 512;
  v107 = v147;
  do
  {
    *(_BYTE *)v107 = 0;
    v107 = (unsigned __int16 *)((char *)v107 + 1);
    --v106;
  }
  while ( v106 );
  v108 = 512;
  Password = v149.Password;
  do
  {
    *(_BYTE *)Password = 0;
    Password = (WCHAR *)((char *)Password + 1);
    --v108;
  }
  while ( v108 );
  v110 = (char *)a2 + 124;
  do
  {
    *v110++ = 0;
    --v102;
  }
  while ( v102 );
  v111 = (char *)this + 14424;
  do
  {
    *v111++ = 0;
    --v105;
  }
  while ( v105 );
  if ( v129 )
    TSCompatShim::FreeMemoryUsingMSVCRT(v129, 0, 0, v13);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v131);
  wil::details::unique_storage_wil::details::resource_policy__WTS_SERIALIZED_USER_CREDENTIAL___void____cdecl____WTS_SERIALIZED_USER_CREDENTIAL_____WTSFreeSerializedUserCredential_wistd::integral_constant_unsigned___int64_0___WTS_SERIALIZED_USER_CREDENTIAL____WTS_SERIALIZED_USER_CREDENTIAL___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy__WTS_SERIALIZED_USER_CREDENTIAL___void____cdecl____WTS_SERIALIZED_USER_CREDENTIAL_____WTSFreeSerializedUserCredential_wistd::integral_constant_unsigned___int64_0___WTS_SERIALIZED_USER_CREDENTIAL____WTS_SERIALIZED_USER_CREDENTIAL___0_std::nullptr_t___(&pMemory);
  return (unsigned int)InstanceOfRemoteConnectionManager;
}

```

## disassembly

```asm
0x1800843d0  push    rbp
0x1800843d2  push    rbx
0x1800843d3  push    rsi
0x1800843d4  push    rdi
0x1800843d5  push    r12
0x1800843d7  push    r13
0x1800843d9  push    r14
0x1800843db  push    r15
0x1800843dd  lea     rbp, [rsp-1598h]
0x1800843e5  mov     eax, 1698h
0x1800843ea  call    _alloca_probe
0x1800843ef  sub     rsp, rax
0x1800843f2  mov     rax, cs:__security_cookie
0x1800843f9  xor     rax, rsp
0x1800843fc  mov     [rbp+15D0h+var_50], rax
0x180084403  mov     r12, r9
0x180084406  mov     rbx, r8
0x180084409  mov     r13, rdx
0x18008440c  mov     rdi, rcx
0x18008440f  mov     rax, [rbp+15D0h+arg_20]
0x180084416  mov     [rbp+15D0h+var_15E8], rax
0x18008441a  xor     edx, edx; Val
0x18008441c  mov     r8d, 600h; Size
0x180084422  lea     rcx, [rbp+15D0h+var_1510]; void *
0x180084429  call    memset_0
0x18008442e  xor     r14d, r14d
0x180084431  mov     [rbp+15D0h+var_15F0], r14
0x180084435  mov     [rbp+15D0h+var_1618], r14d
0x180084439  mov     [rbp+15D0h+pMemory], r14
0x18008443d  mov     [rbp+15D0h+var_1600], r14d
0x180084441  xor     edx, edx; Val
0x180084443  mov     r8d, 0E80h; Size
0x180084449  lea     rcx, [rbp+15D0h+var_F10]; void *
0x180084450  call    memset_0
0x180084455  mov     [rbp+15D0h+var_15E0], r14
0x180084459  lea     esi, [r14+1]
0x18008445d  cmp     [rdi+648h], r14
0x180084464  jz      short loc_1800844A5
0x180084466  mov     eax, [rdi+45D8h]
0x18008446c  sub     eax, 2
0x18008446f  cmp     eax, esi
0x180084471  ja      short loc_1800844A5
0x180084473  xorps   xmm0, xmm0
0x180084476  movups  [rbp+15D0h+Buf1], xmm0
0x18008447a  lea     rdx, [rbp+15D0h+Buf1]; struct _GUID *
0x18008447e  mov     rcx, rdi; this
0x180084481  call    ?GetConnectionGUIDFromProtocol@CConnectionEx@@AEAAXPEAU_GUID@@@Z; CConnectionEx::GetConnectionGUIDFromProtocol(_GUID *)
0x180084486  lea     r8d, [r14+10h]; Size
0x18008448a  lea     rdx, TERMINAL_TYPE_RDP_REMOTEAPP; Buf2
0x180084491  lea     rcx, [rbp+15D0h+Buf1]; Buf1
0x180084495  call    memcmp_0
0x18008449a  test    eax, eax
0x18008449c  jnz     short loc_1800844A5
0x18008449e  or      dword ptr [rdi+2600h], 8
0x1800844a5  mov     r15d, [rdi+2600h]
0x1800844ac  mov     eax, r15d
0x1800844af  shr     eax, 1Dh
0x1800844b2  and     al, sil
0x1800844b5  mov     [rbp+15D0h+var_F10.fDisableCpm], al
0x1800844bb  mov     eax, r15d
0x1800844be  shr     eax, 1Eh
0x1800844c1  and     al, sil
0x1800844c4  mov     [rbp+15D0h+var_F10.fDisableCdm], al
0x1800844ca  mov     eax, r15d
0x1800844cd  shr     eax, 1Fh
0x1800844d0  mov     [rbp+15D0h+var_F10.fDisableCcm], al
0x1800844d6  mov     al, [rdi+2604h]
0x1800844dc  and     al, sil
0x1800844df  mov     [rbp+15D0h+var_F10.fDisableLPT], al
0x1800844e5  mov     ecx, [rdi+2604h]
0x1800844eb  mov     eax, ecx
0x1800844ed  shr     eax, 1
0x1800844ef  and     al, sil
0x1800844f2  mov     [rbp+15D0h+var_F10.fDisableClip], al
0x1800844f8  mov     eax, ecx
0x1800844fa  shr     eax, 0Bh
0x1800844fd  and     al, sil
0x180084500  mov     [rbp+15D0h+var_F10.fDisablePNP], al
0x180084506  mov     eax, r15d
0x180084509  and     eax, esi
0x18008450b  mov     [rbp+15D0h+var_F10.fInheritAutoLogon], eax
0x180084511  mov     eax, r15d
0x180084514  shr     eax, 3
0x180084517  and     eax, esi
0x180084519  mov     [rbp+15D0h+var_F10.fInheritInitialProgram], eax
0x18008451f  shr     ecx, 8
0x180084522  and     ecx, esi
0x180084524  mov     [rbp+15D0h+var_F10.fInheritColorDepth], ecx
0x18008452a  mov     rcx, [rdi+638h]
0x180084531  mov     rax, [rcx]
0x180084534  lea     rdx, [rbp+15D0h+var_F10]
0x18008453b  mov     rax, [rax+28h]
0x18008453f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084544  mov     esi, eax
0x180084546  test    eax, eax
0x180084548  jns     short loc_1800845B6
0x18008454a  mov     ecx, cs:dword_18012E170
0x180084550  cmp     ecx, 3
0x180084553  jbe     loc_18008583D
0x180084559  lea     rax, aInitializeclie; "InitializeClientData"
0x180084560  mov     [rsp+16D0h+var_1658], rax
0x180084565  lea     rax, aThisPtriwrdspr_2; "this->ptrIWRdsProtocolConnection->GetCl"...
0x18008456c  lea     rdx, byte_1801150F7
0x180084573  mov     [rbp+15D0h+LsaHandle], rax
0x180084577  lea     rax, aWarningHresult; "Warning HResult failed"
0x18008457e  mov     [rbp+15D0h+var_1648], rax
0x180084582  lea     rax, [rsp+16D0h+var_1658]
0x180084587  mov     [rsp+16D0h+SourceContext], rax
0x18008458c  lea     rax, [rsp+16D0h+var_1660]
0x180084591  mov     [rsp+16D0h+var_1660], esi
0x180084595  mov     [rsp+16D0h+LocalGroups], rax
0x18008459a  lea     rax, [rbp+15D0h+LsaHandle]
0x18008459e  mov     qword ptr [rsp+16D0h+AuthenticationInformationLength], rax
0x1800845a3  lea     rax, [rbp+15D0h+var_1648]
0x1800845a7  mov     [rsp+16D0h+AuthenticationInformation], rax
0x1800845ac  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800845b1  jmp     loc_18008583D
0x1800845b6  lea     rcx, [rbp+15D0h+var_15E0]; struct IRemoteConnectionManager **
0x1800845ba  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x1800845bf  mov     esi, eax
0x1800845c1  test    eax, eax
0x1800845c3  jns     short loc_1800845F0
0x1800845c5  mov     eax, cs:dword_18012E170
0x1800845cb  cmp     eax, 3
0x1800845ce  jbe     loc_18008583D
0x1800845d4  lea     rax, aInitializeclie; "InitializeClientData"
0x1800845db  mov     [rsp+16D0h+var_1658], rax
0x1800845e0  lea     rax, aGetinstanceofr_2; "GetInstanceOfRemoteConnectionManager"
0x1800845e7  lea     rdx, qword_1801150B8
0x1800845ee  jmp     short loc_180084573
0x1800845f0  mov     rcx, [rbp+15D0h+var_15E0]
0x1800845f4  mov     rax, [rcx]
0x1800845f7  mov     rax, [rax+190h]
0x1800845fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084603  test    eax, eax
0x180084605  jz      short loc_180084617
0x180084607  mov     [rbp+15D0h+var_F10.DisplayDriverName], r14w
0x18008460f  mov     [rbp+15D0h+var_F10.DisplayDeviceName], r14w
0x180084617  mov     dword ptr [rdi+3EB8h], 1
0x180084621  xor     edx, edx; Val
0x180084623  mov     r8d, 468h; Size
0x180084629  mov     rcx, rbx; void *
0x18008462c  call    memset_0
0x180084631  lea     r14, [rdi+2FF0h]
0x180084638  lea     rdx, [rbp+15D0h+var_F10]; struct _WTS_CLIENT_DATA *
0x18008463f  mov     rcx, r14; struct _WRDS_CONNECTION_SETTINGS *
0x180084642  call    ?ConvertWTSClientDataToWRdsConnectionSetting@CHelper@@SAJPEAU_WRDS_CONNECTION_SETTINGS@@PEAU_WTS_CLIENT_DATA@@@Z; CHelper::ConvertWTSClientDataToWRdsConnectionSetting(_WRDS_CONNECTION_SETTINGS *,_WTS_CLIENT_DATA *)
0x180084647  mov     esi, eax
0x180084649  test    eax, eax
0x18008464b  jns     short loc_18008467B
0x18008464d  mov     eax, cs:dword_18012E170
0x180084653  cmp     eax, 3
0x180084656  jbe     loc_18008583D
0x18008465c  lea     rax, aInitializeclie; "InitializeClientData"
0x180084663  mov     [rsp+16D0h+var_1658], rax
0x180084668  lea     rax, aChelperConvert_4; "CHelper::ConvertWTSClientDataToWRdsConn"...
0x18008466f  lea     rdx, byte_180115073
0x180084676  jmp     loc_180084573
0x18008467b  mov     r8, r14; struct _WRDS_CONNECTION_SETTINGS *
0x18008467e  mov     rdx, rbx; struct _WINSTATIONDOCONNECTMSG *
0x180084681  mov     rcx, r13; struct _WINSTATIONCLIENTW *
0x180084684  call    ?ConvertWRdsConnectionSettingToWinStationClient@CHelper@@SAJPEAU_WINSTATIONCLIENTW@@PEAU_WINSTATIONDOCONNECTMSG@@PEAU_WRDS_CONNECTION_SETTINGS@@@Z; CHelper::ConvertWRdsConnectionSettingToWinStationClient(_WINSTATIONCLIENTW *,_WINSTATIONDOCONNECTMSG *,_WRDS_CONNECTION_SETTINGS *)
0x180084689  mov     esi, eax
0x18008468b  xor     r14d, r14d
0x18008468e  test    eax, eax
0x180084690  jns     short loc_1800846C0
0x180084692  mov     eax, cs:dword_18012E170
0x180084698  cmp     eax, 3
0x18008469b  jbe     loc_18008583D
0x1800846a1  lea     rax, aInitializeclie; "InitializeClientData"
0x1800846a8  mov     [rsp+16D0h+var_1658], rax
0x1800846ad  lea     rax, aChelperConvert_3; "CHelper::ConvertWRdsConnectionSettingTo"...
0x1800846b4  lea     rdx, word_18011502E
0x1800846bb  jmp     loc_180084573
0x1800846c0  shr     r15d, 0Ch
0x1800846c4  and     dword ptr [rdi+2600h], 0FFFFFFF6h
0x1800846cb  mov     ecx, [rbp+15D0h+var_F10.fInheritInitialProgram]
0x1800846d1  mov     edx, 1
0x1800846d6  and     ecx, edx
0x1800846d8  shl     ecx, 3
0x1800846db  mov     eax, [rbp+15D0h+var_F10.fInheritAutoLogon]
0x1800846e1  and     eax, edx
0x1800846e3  or      ecx, eax
0x1800846e5  or      [rdi+2600h], ecx
0x1800846eb  btr     dword ptr [rdi+2604h], 8
0x1800846f3  mov     eax, [rbp+15D0h+var_F10.fInheritColorDepth]
0x1800846f9  and     eax, edx
0x1800846fb  shl     eax, 8
0x1800846fe  or      [rdi+2604h], eax
0x180084704  mov     r8, rbx; struct _WINSTATIONDOCONNECTMSG *
0x180084707  mov     rdx, r13; struct _WINSTATIONCLIENTW *
0x18008470a  mov     rcx, rdi; this
0x18008470d  call    ?MergeUserConfig@CConnectionEx@@AEAAJPEAU_WINSTATIONCLIENTW@@PEAU_WINSTATIONDOCONNECTMSG@@@Z; CConnectionEx::MergeUserConfig(_WINSTATIONCLIENTW *,_WINSTATIONDOCONNECTMSG *)
0x180084712  mov     esi, eax
0x180084714  test    eax, eax
0x180084716  jns     short loc_180084746
0x180084718  mov     eax, cs:dword_18012E170
0x18008471e  cmp     eax, 3
0x180084721  jbe     loc_18008583D
0x180084727  lea     rax, aInitializeclie; "InitializeClientData"
0x18008472e  mov     [rsp+16D0h+var_1658], rax
0x180084733  lea     rax, aMergeuserconfi; "MergeUserConfig"
0x18008473a  lea     rdx, byte_180114FE9
0x180084741  jmp     loc_180084573
0x180084746  mov     eax, [rdi+2600h]
0x18008474c  movzx   edx, [rbp+15D0h+var_F10.fDisableCpm]
0x180084753  shl     edx, 1Dh
0x180084756  xor     edx, eax
0x180084758  and     edx, 20000000h
0x18008475e  xor     edx, eax
0x180084760  movzx   ecx, [rbp+15D0h+var_F10.fDisableCdm]
0x180084767  shl     ecx, 1Eh
0x18008476a  and     edx, 3FFFFFFFh
0x180084770  xor     ecx, edx
0x180084772  btr     ecx, 1Fh
0x180084776  movzx   eax, [rbp+15D0h+var_F10.fDisableCcm]
0x18008477d  shl     eax, 1Fh
0x180084780  or      ecx, eax
0x180084782  mov     [rdi+2600h], ecx
0x180084788  mov     eax, [rdi+2604h]
0x18008478e  movzx   ecx, [rbp+15D0h+var_F10.fDisableLPT]
0x180084795  xor     ecx, eax
0x180084797  mov     ebx, 1
0x18008479c  and     ecx, ebx
0x18008479e  xor     ecx, eax
0x1800847a0  movzx   edx, [rbp+15D0h+var_F10.fDisableClip]
0x1800847a7  add     edx, edx
0x1800847a9  xor     edx, ecx
0x1800847ab  and     edx, 2
0x1800847ae  xor     edx, ecx
0x1800847b0  movzx   eax, [rbp+15D0h+var_F10.fDisablePNP]
0x1800847b7  shl     eax, 0Bh
0x1800847ba  xor     eax, edx
0x1800847bc  and     eax, 800h
0x1800847c1  xor     eax, edx
0x1800847c3  mov     [rdi+2604h], eax
0x1800847c9  mov     eax, cs:dword_18012E170
0x1800847cf  cmp     eax, 4
0x1800847d2  jbe     short loc_18008480A
0x1800847d4  mov     rax, [rdi+648h]
0x1800847db  mov     [rsp+16D0h+var_1658], rax
0x1800847e0  lea     rax, aInitClientData; "Init client data0"
0x1800847e7  mov     [rbp+15D0h+LsaHandle], rax
0x1800847eb  lea     rax, [rsp+16D0h+var_1658]
0x1800847f0  mov     qword ptr [rsp+16D0h+AuthenticationInformationLength], rax
0x1800847f5  lea     rax, [rbp+15D0h+LsaHandle]
0x1800847f9  mov     [rsp+16D0h+AuthenticationInformation], rax
0x1800847fe  lea     rdx, byte_180114FAB
0x180084805  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18008480a  cmp     [rdi+648h], r14
0x180084811  jz      loc_180084B78
0x180084817  xorps   xmm0, xmm0
0x18008481a  xor     eax, eax
0x18008481c  movups  xmmword ptr [rbp+15D0h+var_1540], xmm0
0x180084823  mov     qword ptr [rbp+15D0h+var_1540+10h], rax
0x18008482a  mov     rcx, [rdi+638h]
0x180084831  movups  xmm0, cs:PROPERTY_TYPE_GET_RESTRICTED_LOGON
0x180084838  movdqu  xmmword ptr [rbp+15D0h+var_1550.SourceName], xmm0
0x180084840  mov     rax, [rcx]
0x180084843  lea     rdx, [rbp+15D0h+var_1540]
0x18008484a  mov     qword ptr [rsp+16D0h+AuthenticationInformationLength], rdx
0x18008484f  mov     [rsp+16D0h+AuthenticationInformation], r14
0x180084854  mov     r9d, ebx
0x180084857  xor     r8d, r8d
0x18008485a  lea     rdx, [rbp+15D0h+var_1550]
0x180084861  mov     rax, [rax+0C0h]
0x180084868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008486d  mov     esi, eax
0x18008486f  test    eax, eax
0x180084871  jns     short loc_1800848A1
0x180084873  mov     eax, cs:dword_18012E170
0x180084879  cmp     eax, 3
0x18008487c  jbe     loc_18008583D
0x180084882  lea     rax, aInitializeclie; "InitializeClientData"
0x180084889  mov     [rsp+16D0h+var_1658], rax
0x18008488e  lea     rax, aThisPtriwrdspr_12; "this->ptrIWRdsProtocolConnection->Query"...
0x180084895  lea     rdx, word_180114F66
0x18008489c  jmp     loc_180084573
0x1800848a1  mov     eax, dword ptr [rbp+15D0h+var_1540+8]
0x1800848a7  neg     eax
0x1800848a9  sbb     ecx, ecx
0x1800848ab  and     ecx, 1000h
0x1800848b1  btr     dword ptr [r13+0], 0Ch
0x1800848b7  or      [r13+0], ecx
0x1800848bb  mov     rcx, [rdi+638h]
0x1800848c2  movups  xmm0, cs:PROPERTY_TYPE_GET_REDIRECTED_AUTHENTICATION
0x1800848c9  movdqu  xmmword ptr [rbp+15D0h+var_1550.SourceName], xmm0
0x1800848d1  mov     rax, [rcx]
0x1800848d4  lea     rdx, [rbp+15D0h+var_1540]
0x1800848db  mov     qword ptr [rsp+16D0h+AuthenticationInformationLength], rdx
0x1800848e0  mov     [rsp+16D0h+AuthenticationInformation], r14
0x1800848e5  mov     r9d, ebx
0x1800848e8  xor     r8d, r8d
0x1800848eb  lea     rdx, [rbp+15D0h+var_1550]
0x1800848f2  mov     rax, [rax+0C0h]
0x1800848f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800848fe  test    eax, eax
0x180084900  jns     short loc_18008490A
0x180084902  btr     dword ptr [r13+0], 0Dh
0x180084908  jmp     short loc_180084924
  ... truncated ...
```
