# IntfConnectEx(ulong,void *,_WLAN_CONNECTION_PARAMETERS_V2 * const,ulong,int,_WLAN_PRECONNECT_INPUT_RESPONSE * const,void * const,_WLAN_RAW_DATA_LIST * const)

- ea: `0x1800539ac`
- end: `0x1800553e6`
- name: `?IntfConnectEx@@YAKKPEAXQEAU_WLAN_CONNECTION_PARAMETERS_V2@@KHQEAU_WLAN_PRECONNECT_INPUT_RESPONSE@@QEAXQEAU_WLAN_RAW_DATA_LIST@@@Z`
- size: `6714`
- prototype: `unsigned int __fastcall(unsigned int, void *, struct _WLAN_CONNECTION_PARAMETERS_V2 *const, unsigned int, int, struct _WLAN_PRECONNECT_INPUT_RESPONSE *const, void *const, struct _WLAN_RAW_DATA_LIST *const)`
- caller_count: `4`
- callee_count: `52`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800534ec`
- `0x1801496fc`
- `0x1801a3f60`
- `0x1801a68c0`

## callees

- `0x1800042ac`
- `0x18000aa0c`
- `0x18000c5a0`
- `0x180011530`
- `0x180013630`
- `0x180017090`
- `0x180017440`
- `0x180028894`
- `0x180029ca0`
- `0x180029ed4`
- `0x18002f450`
- `0x18003fda0`
- `0x18003fee8`
- `0x180049420`
- `0x180049a54`
- `0x18004c6d4`
- `0x18004f180`
- `0x180052664`
- `0x1800539ac`
- `0x180057454`
- `0x180057afc`
- `0x18005f3d0`
- `0x180066370`
- `0x1800705b8`
- `0x180075f68`
- `0x18007807c`
- `0x180080fec`
- `0x18008228c`
- `0x18009151c`
- `0x180093d2c`
- `0x18009807c`
- `0x18009ad78`
- `0x1800a2c3c`
- `0x1800a53c0`
- `0x1800a82a8`
- `0x1800ac8ac`
- `0x1800b80bc`
- `0x1800c6774`
- `0x1800cfe94`
- `0x180106340`
- `0x180107318`
- `0x1801164a4`
- `0x180136298`
- `0x180146658`
- `0x180147cb8`
- `0x18014899c`
- `0x180152950`
- `0x180154378`
- `0x180162cb8`
- `0x1801b5b68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800543e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800543e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800543a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800543a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800540a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054111`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800541cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005427f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054363`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800540a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054111`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800541cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005427f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054363`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180054337`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180054337`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180053c55`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180053c55`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18005538e`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18005538e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IntfConnectEx(
        unsigned int a1,
        void *a2,
        struct _WLAN_CONNECTION_PARAMETERS_V2 *const a3,
        ULONG a4,
        int a5,
        const WCHAR *a6,
        void *const a7,
        struct _WLAN_RAW_DATA_LIST *const a8)
{
  ULONG v8; // ebx
  const WCHAR *v12; // rcx
  PVOID *v13; // rdi
  PDOT11_SSID pDot11Ssid; // rdx
  __int64 v15; // rdx
  DOT11_BSS_TYPE dot11BssType; // r8d
  __int64 v17; // r12
  unsigned int BssType; // ebx
  __int64 dwFlags; // r9
  LPCWSTR strProfile; // rcx
  __int64 v21; // rax
  __int64 v22; // rsi
  LPCWSTR v23; // rcx
  unsigned __int64 v24; // rax
  unsigned int IsActiveConsoleSession; // eax
  __int64 v26; // rdx
  __int64 v27; // rdx
  unsigned int v28; // edi
  __int64 v29; // r9
  int v30; // eax
  unsigned int v31; // eax
  PDOT11_BSSID_LIST pDesiredBssidList; // r9
  unsigned int uTotalNumOfEntries; // eax
  __int64 uNumOfEntries; // r9
  struct _DOT11_SSID *v35; // rcx
  PDOT11_SSID v36; // rdx
  unsigned int uSSIDLength; // eax
  __int64 v38; // rbx
  __int64 v39; // r9
  DWORD LastError; // eax
  __int64 v41; // rdx
  __int64 v42; // rax
  PDOT11_SSID v43; // rax
  __int64 v44; // rcx
  PDOT11_BSSID_LIST v45; // rcx
  unsigned __int64 v46; // rdx
  unsigned int v47; // eax
  __int64 v48; // rax
  unsigned int v49; // eax
  DWORD v50; // edi
  void *v51; // rax
  DWORD v52; // eax
  int v53; // edi
  DWORD v54; // eax
  HANDLE v55; // r12
  const WCHAR *v56; // rdi
  PVOID v57; // rcx
  int v58; // eax
  bool v59; // zf
  _QWORD *v60; // rdi
  PDOT11_SSID v61; // rdx
  unsigned int v62; // eax
  __int64 v63; // rbx
  __int64 v64; // rdx
  __int64 v65; // r14
  unsigned int TemporaryConfiguration; // eax
  _QWORD *v67; // rcx
  __int64 v68; // rdx
  __int64 v69; // r9
  __int64 v70; // rdi
  __int64 v71; // r9
  enum _DOT11_BSS_TYPE v72; // eax
  const struct _DOT11_SSID *v73; // rcx
  _QWORD *v74; // rdi
  PDOT11_SSID v75; // rdx
  unsigned int v76; // eax
  __int64 v77; // rbx
  __int64 v78; // rdx
  _QWORD *v79; // rcx
  __int64 v80; // rdx
  struct _DOT11_SSID *v81; // rdx
  struct _LIST_ENTRY *v82; // rcx
  PDOT11_SSID v83; // rdx
  unsigned int v84; // eax
  _QWORD *v85; // rcx
  __int64 v86; // rdx
  _WORD *v87; // rdx
  __int64 v88; // rax
  __int64 v89; // rax
  __int64 v90; // rax
  __int64 v91; // rcx
  _QWORD *v92; // r12
  __int64 v93; // r14
  UCHAR *pDot11Hessid; // rdx
  __int64 v95; // r8
  _QWORD *v96; // rax
  __int64 v97; // r9
  const struct _DOT11_SSID *v98; // rcx
  int DoesProfileContainSsid; // eax
  PDOT11_SSID v100; // rdx
  unsigned int v101; // eax
  _QWORD *v102; // rax
  __int64 v103; // rdx
  unsigned int updated; // eax
  PVOID *v105; // rcx
  PDOT11_ACCESSNETWORKOPTIONS pDot11AccessNetworkOptions; // rcx
  struct _DOT11_SSID *v107; // rdx
  struct _LIST_ENTRY *v108; // rcx
  PDOT11_SSID v109; // rdx
  unsigned int v110; // eax
  _DOT11_OI v111; // rdi
  int v112; // ecx
  __int64 v113; // rcx
  unsigned int v114; // ebx
  __int64 v115; // rcx
  __int64 v116; // rax
  __int64 v117; // rax
  __int64 v118; // rax
  __int64 v119; // rcx
  _DOT11_OI **v120; // r14
  unsigned int MsmRuntimeState; // ebx
  _DOT11_OI *v122; // rdi
  int v123; // edx
  _DWORD *v124; // rbx
  __int64 v125; // r8
  _QWORD *v126; // rax
  PDOT11_SSID v127; // rax
  unsigned int v128; // ecx
  _WLAN_CONNECTION_MODE *v129; // rdx
  __int16 v130; // ax
  __int64 v131; // r8
  __int64 v132; // r9
  enum _DOT11_BSS_TYPE v134; // [rsp+20h] [rbp-E0h]
  unsigned __int8 **v135; // [rsp+48h] [rbp-B8h]
  HANDLE ExistingTokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v137; // [rsp+58h] [rbp-A8h] BYREF
  struct _WLAN_INTERFACE_CONTEXT *v138; // [rsp+60h] [rbp-A0h] BYREF
  _DOT11_OI v139; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v140; // [rsp+70h] [rbp-90h] BYREF
  int v141; // [rsp+74h] [rbp-8Ch] BYREF
  ULONG SessionId; // [rsp+78h] [rbp-88h]
  enum _DOT11_BSS_TYPE v143[2]; // [rsp+80h] [rbp-80h] BYREF
  void *v144; // [rsp+88h] [rbp-78h]
  _WLAN_CONNECTION_MODE *v145; // [rsp+90h] [rbp-70h] BYREF
  struct _PM_PROFILE *v146; // [rsp+98h] [rbp-68h] BYREF
  char v147; // [rsp+A0h] [rbp-60h]
  __int128 v148; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v149; // [rsp+B8h] [rbp-48h]
  int v150; // [rsp+C8h] [rbp-38h]
  _WLAN_CONNECTION_MODE v151[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v152; // [rsp+E0h] [rbp-20h]
  int v153; // [rsp+F0h] [rbp-10h]
  _BYTE v154[32]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v155[40]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v156[40]; // [rsp+140h] [rbp+40h] BYREF

  v8 = a4;
  SessionId = a4;
  v144 = a2;
  v12 = a6;
  v137 = a6;
  ExistingTokenHandle = a7;
  v138 = 0;
  v143[0] = 0;
  v140 = 0;
  v141 = 0;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 162, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, a2, a3);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, a2, a3);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  pDot11Ssid = a3->pDot11Ssid;
  if ( pDot11Ssid && pDot11Ssid->uSSIDLength > 0x20 )
  {
    if ( v13 == &WPP_GLOBAL_Control || !*((_BYTE *)v13 + 105) || (*((_BYTE *)v13 + 108) & 1) == 0 )
      goto LABEL_409;
    v15 = 163;
LABEL_408:
    WPP_SF_(v13[12], v15, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
    v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_409:
    BssType = 87;
    goto LABEL_410;
  }
  dot11BssType = a3->dot11BssType;
  if ( (unsigned int)(dot11BssType - 1) > 2 )
  {
    if ( v13 == &WPP_GLOBAL_Control || !*((_BYTE *)v13 + 105) || (*((_BYTE *)v13 + 108) & 1) == 0 )
      goto LABEL_409;
    v15 = 164;
    goto LABEL_408;
  }
  v17 = -1;
  if ( a3->wlanConnectionMode )
  {
    if ( a3->wlanConnectionMode != wlan_connection_mode_temporary_profile )
    {
      if ( (unsigned int)(a3->wlanConnectionMode - 2) <= 1 )
      {
        BssType = pDot11Ssid == 0 ? 0x57 : 0;
        if ( (unsigned int)(dot11BssType - 1) <= 1 )
        {
          if ( pDot11Ssid )
          {
            v8 = SessionId;
            goto LABEL_22;
          }
LABEL_34:
          v22 = 0;
          if ( v13 != &WPP_GLOBAL_Control && *((_BYTE *)v13 + 105) && (*((_BYTE *)v13 + 108) & 1) != 0 )
          {
            WPP_SF_(v13[12], 165, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
LABEL_38:
            v13 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_39;
          }
          goto LABEL_39;
        }
      }
LABEL_33:
      BssType = 87;
      goto LABEL_34;
    }
    strProfile = a3->strProfile;
    if ( !strProfile )
      goto LABEL_33;
    v21 = -1;
    do
      ++v21;
    while ( strProfile[v21] );
    if ( !v21 )
      goto LABEL_33;
  }
  else
  {
    v23 = a3->strProfile;
    if ( !v23 )
      goto LABEL_33;
    v24 = -1;
    do
      ++v24;
    while ( v23[v24] );
    if ( v24 >= 0x100 )
      goto LABEL_33;
  }
LABEL_22:
  dwFlags = a3->dwFlags;
  if ( (dwFlags & 0xFFFFFF80) != 0 )
  {
    if ( v13 == &WPP_GLOBAL_Control || !*((_BYTE *)v13 + 105) || (*((_BYTE *)v13 + 108) & 1) == 0 )
      goto LABEL_28;
    WPP_SF_d(v13[12], 166, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, dwFlags);
LABEL_27:
    v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_28:
    BssType = 87;
    goto LABEL_410;
  }
  IsActiveConsoleSession = AcmIsActiveConsoleSession(v8, &v141);
  BssType = IsActiveConsoleSession;
  if ( IsActiveConsoleSession )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v26 = 167;
LABEL_75:
      v29 = IsActiveConsoleSession;
LABEL_113:
      WPP_SF_d(v13[12], v26, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, v29);
      goto LABEL_64;
    }
    goto LABEL_410;
  }
  IsActiveConsoleSession = HtReferenceHandleWithTag(g_hHandleTable, v144, 1229870150, 0, 1, &v138);
  BssType = IsActiveConsoleSession;
  if ( !IsActiveConsoleSession )
  {
    if ( *((_DWORD *)v138 + 6) == 4 && (unsigned int)(a3->wlanConnectionMode - 2) <= 1 )
    {
      BssType = 50;
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_410;
      }
      v27 = 169;
      goto LABEL_63;
    }
    v28 = v141;
    IsActiveConsoleSession = IntfCheckDisconnectPrivilege(a1, v138, (unsigned int)v141);
    BssType = IsActiveConsoleSession;
    if ( IsActiveConsoleSession )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v26 = 170;
        goto LABEL_75;
      }
      goto LABEL_410;
    }
    IsActiveConsoleSession = IntfCheckConnectPrivilege(a1, v138, a3, v28);
    BssType = IsActiveConsoleSession;
    if ( IsActiveConsoleSession )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v26 = 171;
        goto LABEL_75;
      }
      goto LABEL_410;
    }
    Wim11adGetRefPairedInterfaceContext(&v139, (char *)v138 + 8);
    if ( v139 )
    {
      v30 = *((_DWORD *)v138 + 170);
      if ( v30 )
      {
        if ( (unsigned int)(v30 - 3) > 1 )
        {
          v31 = IntfCheckDisconnectPrivilege(a1, *(struct _WLAN_INTERFACE_CONTEXT **)&v139, v28);
          BssType = v31;
          if ( v31 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 105)
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 172, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, v31);
            }
            wistd::unique_ptr<_WLAN_INTERFACE_CONTEXT,wlansvc::intfctxt_dereferencer>::reset(&v139, 0);
            goto LABEL_64;
          }
        }
      }
    }
    wistd::unique_ptr<_WLAN_INTERFACE_CONTEXT,wlansvc::intfctxt_dereferencer>::reset(&v139, 0);
    pDesiredBssidList = a3->pDesiredBssidList;
    if ( pDesiredBssidList )
    {
      uTotalNumOfEntries = pDesiredBssidList->uTotalNumOfEntries;
      uNumOfEntries = pDesiredBssidList->uNumOfEntries;
      if ( (unsigned int)uNumOfEntries > uTotalNumOfEntries )
      {
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_28;
        }
        v134 = uTotalNumOfEntries;
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          173,
          &WPP_ddf81be17d3f38632d423248857aa840_Traceguids,
          uNumOfEntries);
        goto LABEL_27;
      }
      if ( (unsigned int)uNumOfEntries > *((_DWORD *)v138 + 52) )
      {
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_97;
        }
        v134 = *((_DWORD *)v138 + 52);
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          174,
          &WPP_ddf81be17d3f38632d423248857aa840_Traceguids,
          uNumOfEntries);
LABEL_96:
        v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_97:
        BssType = 50;
        goto LABEL_410;
      }
    }
    v35 = a3->pDot11Ssid;
    if ( v35
      && (*((_BYTE *)v138 + 24) & 0x10) == 0
      && !(unsigned int)WimIsNetworkPermitted(v35, a3->dot11BssType, &v140) )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v36 = a3->pDot11Ssid;
        uSSIDLength = v36->uSSIDLength;
        if ( v36->uSSIDLength > 0x20 )
          uSSIDLength = 32;
        v38 = uSSIDLength;
        memcpy_0(v156, v36->ucSSID, uSSIDLength);
        v156[v38] = 0;
        WPP_SF_s(v13[12], 175, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
        v13 = (PVOID *)WPP_GLOBAL_Control;
      }
      BssType = 1399;
      goto LABEL_410;
    }
    if ( *((_DWORD *)v138 + 565) )
    {
      BssType = -2144067582;
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v26 = 176;
        v29 = 2150899714LL;
        goto LABEL_113;
      }
      goto LABEL_410;
    }
    BssType = IntfQueryBssType(v144, v143, 0);
    if ( BssType )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_410;
      }
      v27 = 177;
LABEL_63:
      WPP_SF_(v13[12], v27, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
LABEL_64:
      v13 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_410;
    }
    if ( v143[0] != dot11_BSS_type_any )
    {
      v39 = (unsigned int)a3->dot11BssType;
      if ( v143[0] != (_DWORD)v39 )
      {
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_97;
        }
        v134 = v143[0];
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 12), 178, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, v39);
        goto LABEL_96;
      }
    }
    v22 = AllocWLMem(0x320u);
    if ( !v22 )
    {
      LastError = GetLastError();
      BssType = LastError;
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v41 = 179;
LABEL_130:
        WPP_SF_d(v13[12], v41, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, LastError);
        goto LABEL_38;
      }
      goto LABEL_39;
    }
    v42 = AllocWLMem(0x30u);
    *(_QWORD *)(v22 + 608) = v42;
    if ( !v42 )
    {
      LastError = GetLastError();
      BssType = LastError;
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v41 = 180;
        goto LABEL_130;
      }
LABEL_39:
      if ( !BssType || !v22 )
        goto LABEL_410;
LABEL_369:
      CfgFreeSelection((struct WLAN_CONFIG_SELECTION *)v22);
      goto LABEL_64;
    }
    if ( a3->pDot11Ssid )
    {
      *(_DWORD *)(v42 + 4) = 1;
      *(_DWORD *)(*(_QWORD *)(v22 + 608) + 8LL) = 1;
      v43 = a3->pDot11Ssid;
      v44 = *(_QWORD *)(v22 + 608);
      *(_OWORD *)(v44 + 12) = *(_OWORD *)&v43->uSSIDLength;
      *(_OWORD *)(v44 + 28) = *(_OWORD *)&v43->ucSSID[12];
      *(_DWORD *)(v44 + 44) = *(_DWORD *)&v43->ucSSID[28];
    }
    else
    {
      *(_DWORD *)(v42 + 4) = 0;
      *(_DWORD *)(*(_QWORD *)(v22 + 608) + 8LL) = 0;
    }
    v45 = a3->pDesiredBssidList;
    if ( v45 )
    {
      v46 = 1;
      if ( v45->uTotalNumOfEntries )
        v46 = v45->uTotalNumOfEntries;
      v47 = SafeVariableListBufferSize(0xCu, v46, 6u);
      v48 = AllocWLMem(v47);
      *(_QWORD *)(v22 + 632) = v48;
      if ( !v48 )
      {
        LastError = GetLastError();
        BssType = LastError;
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          v41 = 181;
          goto LABEL_130;
        }
        goto LABEL_39;
      }
      v49 = SafeVariableListBufferSize(0xCu, a3->pDesiredBssidList->uTotalNumOfEntries, 6u);
      memcpy_0(*(void **)(v22 + 632), a3->pDesiredBssidList, v49);
    }
    *(_DWORD *)(v22 + 656) = a3->wlanConnectionMode;
    *(_QWORD *)(v22 + 672) = 0;
    *(_DWORD *)(v22 + 664) = 0;
    if ( a8 )
    {
      v50 = a8->dwTotalSize - 8 * a8->dwNumberOfItems - 8;
      v51 = (void *)AllocWLMem(v50);
      *(_QWORD *)(v22 + 672) = v51;
      if ( v51 )
      {
        *(_DWORD *)(v22 + 664) = v50;
        memcpy_0(v51, (char *)a8 + a8->dwTotalSize - (unsigned __int64)v50, v50);
      }
      else
      {
        *(_DWORD *)(v22 + 664) = 0;
        v52 = GetLastError();
        BssType = v52;
        if ( v52 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105)
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 182, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, v52);
          }
          goto LABEL_369;
        }
      }
      v28 = v141;
    }
    *(_DWORD *)(v22 + 680) = SessionId;
    *(_DWORD *)(v22 + 624) = a3->dot11BssType;
    *(_DWORD *)(v22 + 640) = a3->dwFlags;
    *(_DWORD *)(v22 + 776) = v28;
    v53 = (int)ExistingTokenHandle;
    if ( ExistingTokenHandle )
    {
      if ( !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, (PHANDLE)(v22 + 688)) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          v54 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 183, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, v54);
        }
        *(_QWORD *)(v22 + 688) = 0;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 184, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
      }
      *(_QWORD *)(v22 + 688) = 0;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v138 + 144));
    if ( a3->wlanConnectionMode )
    {
      if ( a3->wlanConnectionMode != wlan_connection_mode_temporary_profile )
      {
        if ( a3->wlanConnectionMode == wlan_connection_mode_discovery_secure )
        {
          *(_DWORD *)(v22 + 764) = 1;
        }
        else if ( a3->wlanConnectionMode != wlan_connection_mode_discovery_unsecure )
        {
LABEL_169:
          BssType = 87;
          goto LABEL_170;
        }
        if ( !CfgNetworkOnlyUseGPProfiles((struct _LIST_ENTRY *)v138 + 46, a3->pDot11Ssid, a3->dot11BssType, &v140) )
        {
          BssType = CfgGenerateDiscoveryProfile((struct WLAN_CONFIG_SELECTION *)v22);
          if ( !BssType
            && (g_bMacAddressRandomizationDisabled
             || !*((_DWORD *)v138 + 58)
             || *((_DWORD *)v138 + 59)
             || !*((_DWORD *)v138 + 60)) )
          {
            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v22 + 600) + 552LL) + 24LL) |= 0x10u;
          }
          goto LABEL_170;
        }
        v60 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
LABEL_189:
          BssType = 1399;
          goto LABEL_170;
        }
        v61 = a3->pDot11Ssid;
        v62 = v61->uSSIDLength;
        if ( v61->uSSIDLength > 0x20 )
          v62 = 32;
        v63 = v62;
        memcpy_0(v155, v61->ucSSID, v62);
        v64 = 206;
LABEL_188:
        v155[v63] = 0;
        WPP_SF_s(v60[12], v64, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
        goto LABEL_189;
      }
      v65 = v22 + 584;
      TemporaryConfiguration = CfgCreateTemporaryConfiguration(
                                 (const struct _GUID *)((char *)v138 + 8),
                                 a3->strProfile,
                                 a5 != 0,
                                 (struct wlansvc::RuntimeConfig **)(v22 + 584));
      BssType = TemporaryConfiguration;
      if ( TemporaryConfiguration )
      {
        v67 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_170;
        }
        v68 = 200;
        v69 = TemporaryConfiguration;
        goto LABEL_201;
      }
      v70 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v65 + 24LL) + 552LL);
      *(_DWORD *)(v22 + 764) = *(unsigned __int8 *)(*(_QWORD *)v65 + 36LL);
      v71 = (unsigned int)a3->dot11BssType;
      v72 = *(_DWORD *)(v70 + 16);
      if ( (_DWORD)v71 == 3 )
      {
        *(_DWORD *)(v22 + 624) = v72;
        goto LABEL_204;
      }
      if ( (_DWORD)v71 == v72 )
      {
LABEL_204:
        v73 = a3->pDot11Ssid;
        if ( v73 && !(unsigned int)SsidLookupDoesProfileContainSsid(v73, (struct _DOT11_AC_PROFILE *)v70) )
        {
          v74 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
          {
            goto LABEL_169;
          }
          v75 = a3->pDot11Ssid;
          v76 = v75->uSSIDLength;
          if ( v75->uSSIDLength > 0x20 )
            v76 = 32;
          v77 = v76;
          memcpy_0(v155, v75->ucSSID, v76);
          v78 = 202;
          goto LABEL_212;
        }
        v81 = a3->pDot11Ssid;
        v82 = (struct _LIST_ENTRY *)((char *)v138 + 736);
        if ( v81 )
        {
          if ( CfgNetworkOnlyUseGPProfiles(v82, v81, *(enum _DOT11_BSS_TYPE *)(v22 + 624), &v140) )
          {
            v60 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
            {
              goto LABEL_189;
            }
            v83 = a3->pDot11Ssid;
            v84 = v83->uSSIDLength;
            if ( v83->uSSIDLength > 0x20 )
              v84 = 32;
            v63 = v84;
            memcpy_0(v155, v83->ucSSID, v84);
            v64 = 203;
            goto LABEL_188;
          }
        }
        else if ( (unsigned int)CfgIsProfileGPOnly(v82, (struct _DOT11_AC_PROFILE *)v70, &v140) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 204, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
          }
          goto LABEL_189;
        }
        if ( *(_DWORD *)(v70 + 20) != 8 && *(_DWORD *)(v70 + 20) != 32
          || *((_DWORD *)v138 + 49)
          || *((_DWORD *)v138 + 6) != 2 )
        {
          v87 = (_WORD *)(*(_QWORD *)(*(_QWORD *)v65 + 24LL) + 24LL);
          do
            ++v17;
          while ( v87[v17] );
          memcpy_0((void *)(v22 + 24), v87, 2 * v17);
          v88 = *(_QWORD *)(v70 + 8);
          if ( v88 && *(_DWORD *)(v88 + 4) == 1 )
          {
            v89 = *(_QWORD *)(v22 + 608);
            v55 = ExistingTokenHandle;
            if ( !*(_DWORD *)(v89 + 8) )
            {
              *(_DWORD *)(v89 + 4) = 1;
              *(_DWORD *)(*(_QWORD *)(v22 + 608) + 8LL) = 1;
              v90 = *(_QWORD *)(v70 + 8);
              v91 = *(_QWORD *)(v22 + 608);
              *(_OWORD *)(v91 + 12) = *(_OWORD *)(v90 + 12);
              *(_OWORD *)(v91 + 28) = *(_OWORD *)(v90 + 28);
              *(_DWORD *)(v91 + 44) = *(_DWORD *)(v90 + 44);
            }
            goto LABEL_171;
          }
LABEL_170:
          v55 = ExistingTokenHandle;
LABEL_171:
          v56 = v137;
          goto LABEL_172;
        }
        v85 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
LABEL_241:
          BssType = 50;
          goto LABEL_170;
        }
        v86 = 205;
LABEL_240:
        WPP_SF_(v85[12], v86, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
        goto LABEL_241;
      }
      v79 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_169;
      }
      v80 = 201;
LABEL_218:
      v134 = v72;
      WPP_SF_DD(v79[12], v80, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, v71);
      goto LABEL_169;
    }
    v92 = (_QWORD *)(v22 + 584);
    BssType = CfgGetConfiguration(
                (struct _LIST_ENTRY *)v138 + 46,
                a3->strProfile,
                (struct wlansvc::RuntimeConfig **)(v22 + 584));
    if ( BssType )
    {
      v67 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_170;
      }
      v68 = 185;
      v69 = BssType;
LABEL_201:
      WPP_SF_d(v67[12], v68, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, v69);
      goto LABEL_170;
    }
    if ( !*v92 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          186,
          &WPP_ddf81be17d3f38632d423248857aa840_Traceguids,
          a3->strProfile);
      }
      goto LABEL_169;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        187,
        &WPP_ddf81be17d3f38632d423248857aa840_Traceguids,
        a3->strProfile);
    }
    CfgClearRuntimeInfo(*((unsigned int *)v138 + 6), (char *)v138 + 8, *v92, 7);
    v93 = *(_QWORD *)(*(_QWORD *)(*v92 + 24LL) + 552LL);
    if ( (int)StringCchCopyW((unsigned __int16 *)(v22 + 24), 0x100u, a3->strProfile) < 0 )
      goto LABEL_169;
    CfgCopyProfileGuid(*(struct _PM_PROFILE **)(*v92 + 24LL), (struct _GUID *)(v22 + 536));
    v71 = (unsigned int)a3->dot11BssType;
    v72 = *(_DWORD *)(v93 + 16);
    if ( (_DWORD)v71 == 3 )
    {
      *(_DWORD *)(v22 + 624) = v72;
    }
    else if ( (_DWORD)v71 != v72 )
    {
      v79 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_169;
      }
      v80 = 188;
      goto LABEL_218;
    }
    v96 = *(_QWORD **)(v93 + 56);
    v97 = 0;
    if ( !v96 || !*v96 )
    {
      v98 = a3->pDot11Ssid;
      if ( v98 )
      {
        DoesProfileContainSsid = SsidLookupDoesProfileContainSsid(v98, (struct _DOT11_AC_PROFILE *)v93);
        v97 = 0;
        if ( !DoesProfileContainSsid )
        {
          v74 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
          {
            goto LABEL_169;
          }
          v100 = a3->pDot11Ssid;
          v101 = v100->uSSIDLength;
          if ( v100->uSSIDLength > 0x20 )
            v101 = 32;
          v77 = v101;
          memcpy_0(v155, v100->ucSSID, v101);
          v78 = 189;
LABEL_212:
          v155[v77] = 0;
          WPP_SF_s(v74[12], v78, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
          goto LABEL_169;
        }
      }
    }
    v102 = *(_QWORD **)(v93 + 56);
    if ( v102 && *v102 )
    {
      *(_DWORD *)(v22 + 780) = -1;
      v139 = 0;
      v143[0] = 0;
      BssType = AnqpCacheCheckIfDomainOrRoamingMatches(
                  a3->pDot11Ssid,
                  a3->pDot11Hessid,
                  (const struct _DOT11_AC_PROFILE *)v93,
                  (enum ANQP_NETWORK_ASSOCIATION_TYPE *)v143,
                  &v139);
      if ( BssType )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 190, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
        }
        goto LABEL_170;
      }
      LOBYTE(v103) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_WlanRoamingConsortiumSupport>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_WlanRoamingConsortiumSupport>::GetImpl'::`2'::impl,
        v103);
      if ( v139.OILength
        && (updated = CfgUpdateSelectionWithRcOiIe(v139, (struct WLAN_CONFIG_SELECTION *)v22),
            BssType = updated,
            v97 = 0,
            updated) )
      {
        v105 = (PVOID *)WPP_GLOBAL_Control;
        pDot11Hessid = (UCHAR *)&WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 191, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, updated);
          v105 = (PVOID *)WPP_GLOBAL_Control;
          v97 = 0;
        }
        BssType = 0;
      }
      else
      {
        v105 = (PVOID *)WPP_GLOBAL_Control;
      }
      v95 = (unsigned int)v143[0];
      if ( v143[0] )
      {
        pDot11Hessid = (UCHAR *)a3->pDot11Hessid;
        if ( pDot11Hessid )
        {
          *(_DWORD *)(v22 + 616) = *(_DWORD *)pDot11Hessid;
          *(_WORD *)(v22 + 620) = *((_WORD *)pDot11Hessid + 2);
          pDot11AccessNetworkOptions = a3->pDot11AccessNetworkOptions;
          if ( !pDot11AccessNetworkOptions )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 192, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
            }
            goto LABEL_169;
          }
          *(_DWORD *)(v22 + 788) = *(_DWORD *)&pDot11AccessNetworkOptions->AccessNetworkType;
          *(_BYTE *)(v22 + 792) = pDot11AccessNetworkOptions->UESA;
          v105 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
      if ( (_DWORD)v95 == 1 )
      {
        *(_DWORD *)(v22 + 784) |= 1u;
      }
      else if ( (_DWORD)v95 == 2 )
      {
        *(_DWORD *)(v22 + 784) |= 2u;
      }
      else
      {
        if ( v105 != &WPP_GLOBAL_Control && *((_BYTE *)v105 + 105) >= 2u && (*((_BYTE *)v105 + 108) & 1) != 0 )
          WPP_SF_(v105[12], 193, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
        BssType = 87;
      }
    }
    if ( (*(_BYTE *)(*v92 + 32LL) & 1) == 0 )
    {
      v107 = a3->pDot11Ssid;
      v108 = (struct _LIST_ENTRY *)((char *)v138 + 736);
      if ( v107 )
      {
        if ( CfgNetworkOnlyUseGPProfiles(v108, v107, *(enum _DOT11_BSS_TYPE *)(v22 + 624), &v140) )
        {
          v60 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
          {
            goto LABEL_189;
          }
          v109 = a3->pDot11Ssid;
          v110 = v109->uSSIDLength;
          if ( v109->uSSIDLength > 0x20 )
            v110 = 32;
          v63 = v110;
          memcpy_0(v155, v109->ucSSID, v110);
          v64 = 194;
          goto LABEL_188;
        }
      }
      else if ( (unsigned int)CfgIsProfileGPOnly(v108, (struct _DOT11_AC_PROFILE *)v93, &v140) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            195,
            &WPP_ddf81be17d3f38632d423248857aa840_Traceguids,
            a3->strProfile);
        }
        goto LABEL_189;
      }
    }
    v143[0] = 0;
    v139 = 0;
    if ( !(unsigned int)GetBooleanWiFiMDMPolicy(2, pDot11Hessid, v95, v97) )
    {
      BssType = wlansvc::profile::GetProfileMetaData(
                  (wlansvc::profile *)1,
                  v53,
                  (char *)v138 + 8,
                  (const struct _GUID *)1,
                  *(_DWORD *)(*v92 + 24LL) + 24,
                  0,
                  (struct _PM_PROFILE *)L"Connection Type",
                  (const unsigned __int16 *)v143,
                  (unsigned int *)&v139,
                  v135);
      v111 = v139;
      if ( BssType )
        goto LABEL_339;
      if ( v139 )
      {
        if ( **(_DWORD **)&v139 == 8 )
        {
          ((void (__fastcall *)(_QWORD))FreeWLMem)(v139);
          goto LABEL_331;
        }
LABEL_339:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_Sdd(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            196,
            (unsigned int)&WPP_ddf81be17d3f38632d423248857aa840_Traceguids,
            *(_QWORD *)(*v92 + 24LL) + 24,
            BssType,
            **(_DWORD **)&v139);
        }
        if ( v111 )
          ((void (__fastcall *)(_QWORD))FreeWLMem)(v111);
        goto LABEL_189;
      }
    }
LABEL_331:
    v112 = *(_DWORD *)(v93 + 20);
    if ( v112 == 8 || v112 == 32 )
    {
      if ( !*((_DWORD *)v138 + 49) && *((_DWORD *)v138 + 6) == 2 )
      {
        v85 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_241;
        }
        v86 = 197;
        goto LABEL_240;
      }
      *(_DWORD *)(*(_QWORD *)(v93 + 32) + 396LL) = *((_DWORD *)v138 + 809);
    }
    v113 = *v92;
    *(_DWORD *)(v22 + 764) = *(unsigned __int8 *)(*v92 + 36LL);
    v56 = v137;
    if ( v137 )
    {
      v145 = (_WLAN_CONNECTION_MODE *)(v22 + 600);
      v146 = 0;
      v147 = 1;
      v114 = PmCopyProfile(*(struct _PM_PROFILE **)(v113 + 24), &v146);
      wil::details::out_param_t<wistd::unique_ptr<_PM_PROFILE,wil::function_deleter<void (*)(_PM_PROFILE *),&void PmFreeProfile(_PM_PROFILE *)>>>::~out_param_t<wistd::unique_ptr<_PM_PROFILE,wil::function_deleter<void (*)(_PM_PROFILE *),&void PmFreeProfile(_PM_PROFILE *)>>>(&v145);
      if ( v114
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 198, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, v114);
      }
      v115 = *v92;
      v55 = ExistingTokenHandle;
      BssType = WlanCreatePlapRuntimeState(
                  *(struct _PM_PROFILE **)(v115 + 24),
                  *((_DWORD *)v137 + 1) / 0xA14u,
                  (struct _PLAP_INPUT_FIELD_DATA *)(v137 + 8),
                  ExistingTokenHandle,
                  (void **)(v22 + 752));
      if ( BssType
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 199, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, BssType);
      }
    }
    else
    {
      v55 = ExistingTokenHandle;
    }
    v116 = *(_QWORD *)(v93 + 8);
    if ( v116 )
    {
      if ( *(_DWORD *)(v116 + 4) == 1 )
      {
        v117 = *(_QWORD *)(v22 + 608);
        if ( !*(_DWORD *)(v117 + 8) )
        {
          *(_DWORD *)(v117 + 4) = 1;
          *(_DWORD *)(*(_QWORD *)(v22 + 608) + 8LL) = 1;
          v118 = *(_QWORD *)(v93 + 8);
          v119 = *(_QWORD *)(v22 + 608);
          *(_OWORD *)(v119 + 12) = *(_OWORD *)(v118 + 12);
          *(_OWORD *)(v119 + 28) = *(_OWORD *)(v118 + 28);
          *(_DWORD *)(v119 + 44) = *(_DWORD *)(v118 + 44);
        }
      }
    }
LABEL_172:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v138 + 144));
    if ( BssType )
      goto LABEL_369;
    v58 = *(_DWORD *)(v22 + 624);
    if ( v58 == 1 )
    {
      v59 = (*(_BYTE *)(v22 + 640) & 2) == 0;
    }
    else
    {
      if ( v58 != 2 )
      {
LABEL_365:
        if ( ((*(_BYTE *)(v22 + 640) & 0xC) == 0 || v58 != 2 && *(_DWORD *)(v22 + 656) == 1)
          && ((a3->dwFlags & 0x70) == 0 || (unsigned int)(a3->wlanConnectionMode - 2) <= 1)
          && ((a3->dwFlags & 0x60) == 0 || (a3->dwFlags & 0x10) != 0) )
        {
          if ( (unsigned int)(*(_DWORD *)(v22 + 656) - 2) > 1 )
            goto LABEL_387;
          v120 = (_DOT11_OI **)(v22 + 752);
          if ( v56 )
          {
            v139 = 0;
            *v120 = 0;
            v122 = (_DOT11_OI *)AllocWLMem(8u);
            if ( v122 )
            {
              MsmRuntimeState = MSMSecCreateRunTimeStateWithPreConnectInput(v137, &v139);
              if ( !MsmRuntimeState )
              {
                *v122 = v139;
                *v120 = v122;
                goto LABEL_380;
              }
            }
            else
            {
              MsmRuntimeState = 14;
            }
            MsmFreeRuntimeState(v122);
          }
          else
          {
            MsmRuntimeState = CreateMsmRuntimeState(SessionId, v55, (void **)(v22 + 752));
          }
LABEL_380:
          if ( MsmRuntimeState )
          {
            v57 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 105)
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                207,
                &WPP_ddf81be17d3f38632d423248857aa840_Traceguids,
                MsmRuntimeState);
            }
          }
LABEL_387:
          v124 = *(_DWORD **)(wil::details::static_lazy<WlanTriageProvider>::get(v57) + 8);
          if ( *v124 <= 4u || !(unsigned __int8)tlgKeywordOn(v124, 4, v125) )
            goto LABEL_397;
          v126 = (_QWORD *)stringify::ConnectionParamFlagsToLogString(v154, a3->dwFlags);
          if ( v126[3] > 0xFu )
            v126 = (_QWORD *)*v126;
          v139 = (_DOT11_OI)v126;
          v127 = a3->pDot11Ssid;
          if ( v127 )
          {
            v128 = v127->uSSIDLength;
            v148 = 0;
            v149 = 0;
            v150 = 0;
            v148 = *(_OWORD *)&v127->uSSIDLength;
            v149 = *(_OWORD *)&v127->ucSSID[12];
            v150 = *(_DWORD *)&v127->ucSSID[28];
            v129 = (_WLAN_CONNECTION_MODE *)&v148 + 1;
            v130 = -1;
            if ( v128 > 0xFFFF )
              goto LABEL_396;
          }
          else
          {
            *(_OWORD *)v151 = 0;
            v152 = 0;
            v153 = 0;
            v129 = &v151[1];
            LOWORD(v128) = 0;
          }
          v130 = v128;
LABEL_396:
          v145 = v129;
          LOWORD(v146) = v130;
          v137 = (const WCHAR *)(v22 + 24);
          ExistingTokenHandle = (HANDLE)stringify::ToLogString(
                                          (stringify *)(unsigned int)a3->wlanConnectionMode,
                                          (enum _WLAN_CONNECTION_MODE)v129);
          *(_QWORD *)v143 = (char *)v138 + 8;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperArray<1>,_tlgWrapSz<char>>(
            (__int64)v124,
            (__int64)&word_180276A56,
            v131,
            v132,
            (__int64 *)v143,
            (__int64 **)&ExistingTokenHandle,
            &v137,
            (__int64 *)&v145,
            (__int64 **)&v139);
          std::string::~string(v154);
LABEL_397:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            WPP_SF_DDSD(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              SessionId,
              v125,
              *(_DWORD *)(v22 + 656),
              *(_DWORD *)(v22 + 640),
              v22 + 24,
              SessionId);
          }
          if ( (byte_1802A0A42 & 4) != 0 )
            McTemplateU0jzqqzp_EventWriteTransfer(
              v22 + 24,
              v123,
              (_DWORD)v138 + 8,
              *((_QWORD *)v138 + 16),
              *(_DWORD *)(v22 + 656),
              *(_DWORD *)(v22 + 640),
              v22 + 24,
              *(_DWORD *)(v22 + 680));
          WlanAcmSqmConnect(*(unsigned int *)(v22 + 640), (unsigned int)v141, *(unsigned int *)(v22 + 656));
          BssType = IntfCommandHandler(*(void **)v138, 0x8000000u, (void *)v22, 0x320u);
          goto LABEL_38;
        }
LABEL_368:
        BssType = 87;
        goto LABEL_369;
      }
      v59 = (*(_BYTE *)(v22 + 640) & 1) == 0;
    }
    if ( !v59 )
      goto LABEL_368;
    goto LABEL_365;
  }
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105)
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    v26 = 168;
    goto LABEL_75;
  }
LABEL_410:
  if ( v138 )
  {
    TrAddInterfaceTrace(*((_QWORD *)v138 + 410), 0, *((_QWORD *)v138 + 86), BssType, v134);
    HtDereferenceHandleWithTag(g_hHandleTable, v144, 0, 1);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && *((_BYTE *)v13 + 105) >= 4u && (*((_BYTE *)v13 + 108) & 1) != 0 )
    WPP_SF_d(v13[12], 209, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, BssType);
  return BssType;
}

```

## disassembly

```asm
0x1800539ac  push    rbp
0x1800539ae  push    rbx
0x1800539af  push    rsi
0x1800539b0  push    rdi
0x1800539b1  push    r12
0x1800539b3  push    r13
0x1800539b5  push    r14
0x1800539b7  push    r15
0x1800539b9  lea     rbp, [rsp-78h]
0x1800539be  sub     rsp, 178h
0x1800539c5  mov     rax, cs:__security_cookie
0x1800539cc  xor     rax, rsp
0x1800539cf  mov     [rbp+0B0h+var_48], rax
0x1800539d3  mov     ebx, r9d
0x1800539d6  mov     [rsp+1B0h+SessionId], ebx
0x1800539da  mov     r15, r8
0x1800539dd  mov     r13, rdx
0x1800539e0  mov     [rbp+0B0h+var_128], rdx
0x1800539e4  mov     esi, ecx
0x1800539e6  mov     r14, [rbp+0B0h+arg_38]
0x1800539ed  mov     rcx, [rbp+0B0h+arg_28]
0x1800539f4  mov     [rsp+1B0h+var_158], rcx
0x1800539f9  mov     r12, [rbp+0B0h+arg_30]
0x180053a00  mov     [rsp+1B0h+ExistingTokenHandle], r12
0x180053a05  xor     r9d, r9d
0x180053a08  mov     [rsp+1B0h+var_150], r9
0x180053a0d  mov     [rbp+0B0h+var_130], r9d
0x180053a11  mov     [rsp+1B0h+var_140], r9d
0x180053a16  mov     [rsp+1B0h+var_13C], r9d
0x180053a1b  lea     r12, WPP_GLOBAL_Control
0x180053a22  mov     rdi, cs:WPP_GLOBAL_Control
0x180053a29  cmp     rdi, r12
0x180053a2c  jz      short loc_180053A59
0x180053a2e  cmp     byte ptr [rdi+69h], 4
0x180053a32  jb      short loc_180053A59
0x180053a34  test    byte ptr [rdi+6Ch], 1
0x180053a38  jz      short loc_180053A59
0x180053a3a  mov     edx, 0A2h
0x180053a3f  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x180053a46  mov     rcx, [rdi+60h]
0x180053a4a  call    WPP_SF_
0x180053a4f  mov     rdi, cs:WPP_GLOBAL_Control
0x180053a56  xor     r9d, r9d
0x180053a59  test    r13, r13
0x180053a5c  jnz     short loc_180053A6D
0x180053a5e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "hInterfaceContext != nullptr")
0x180053a63  mov     rdi, cs:WPP_GLOBAL_Control
0x180053a6a  xor     r9d, r9d
0x180053a6d  test    r15, r15
0x180053a70  jnz     short loc_180053A81
0x180053a72  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pConnPara != nullptr")
0x180053a77  mov     rdi, cs:WPP_GLOBAL_Control
0x180053a7e  xor     r9d, r9d
0x180053a81  mov     rdx, [r15+10h]
0x180053a85  test    rdx, rdx
0x180053a88  jz      short loc_180053AB6
0x180053a8a  cmp     dword ptr [rdx], 20h ; ' '
0x180053a8d  jbe     short loc_180053AB6
0x180053a8f  cmp     rdi, r12
0x180053a92  jz      loc_180055353
0x180053a98  cmp     byte ptr [rdi+69h], 1
0x180053a9c  jb      loc_180055353
0x180053aa2  test    byte ptr [rdi+6Ch], 1
0x180053aa6  jz      loc_180055353
0x180053aac  mov     edx, 0A3h
0x180053ab1  jmp     loc_18005533C
0x180053ab6  mov     r8d, [r15+28h]
0x180053aba  lea     eax, [r8-1]
0x180053abe  cmp     eax, 2
0x180053ac1  ja      loc_180055326
0x180053ac7  mov     ecx, [r15]
0x180053aca  or      r12, 0FFFFFFFFFFFFFFFFh
0x180053ace  lea     r13d, [r12+58h]
0x180053ad3  test    ecx, ecx
0x180053ad5  jz      loc_180053BC5
0x180053adb  sub     ecx, 1
0x180053ade  jz      short loc_180053B5A
0x180053ae0  sub     ecx, 1
0x180053ae3  jz      short loc_180053AEE
0x180053ae5  cmp     ecx, 1
0x180053ae8  jnz     loc_180053B75
0x180053aee  mov     rax, rdx
0x180053af1  neg     rax
0x180053af4  sbb     ebx, ebx
0x180053af6  not     ebx
0x180053af8  and     ebx, r13d
0x180053afb  lea     eax, [r8-1]
0x180053aff  cmp     eax, 1
0x180053b02  ja      short loc_180053B75
0x180053b04  test    rdx, rdx
0x180053b07  jz      short loc_180053B78
0x180053b09  mov     ebx, [rsp+1B0h+SessionId]
0x180053b0d  mov     r9d, [r15+2Ch]
0x180053b11  test    r9d, 0FFFFFF80h
0x180053b18  jz      loc_180053BE8
0x180053b1e  lea     r12, WPP_GLOBAL_Control
0x180053b25  cmp     rdi, r12
0x180053b28  jz      short loc_180053B52
0x180053b2a  cmp     byte ptr [rdi+69h], 1
0x180053b2e  jb      short loc_180053B52
0x180053b30  test    byte ptr [rdi+6Ch], 1
0x180053b34  jz      short loc_180053B52
0x180053b36  mov     edx, 0A6h
0x180053b3b  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x180053b42  mov     rcx, [rdi+60h]
0x180053b46  call    WPP_SF_d
0x180053b4b  mov     rdi, cs:WPP_GLOBAL_Control
0x180053b52  mov     ebx, r13d
0x180053b55  jmp     loc_180055358
0x180053b5a  mov     rcx, [r15+8]
0x180053b5e  test    rcx, rcx
0x180053b61  jz      short loc_180053B75
0x180053b63  mov     rax, r12
0x180053b66  inc     rax
0x180053b69  cmp     [rcx+rax*2], r9w
0x180053b6e  jnz     short loc_180053B66
0x180053b70  test    rax, rax
0x180053b73  jnz     short loc_180053B0D
0x180053b75  mov     ebx, r13d
0x180053b78  mov     rsi, r9
0x180053b7b  lea     r12, WPP_GLOBAL_Control
0x180053b82  cmp     rdi, r12
0x180053b85  jz      short loc_180053BAF
0x180053b87  cmp     byte ptr [rdi+69h], 1
0x180053b8b  jb      short loc_180053BAF
0x180053b8d  test    byte ptr [rdi+6Ch], 1
0x180053b91  jz      short loc_180053BAF
0x180053b93  mov     edx, 0A5h
0x180053b98  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x180053b9f  mov     rcx, [rdi+60h]
0x180053ba3  call    WPP_SF_
0x180053ba8  mov     rdi, cs:WPP_GLOBAL_Control
0x180053baf  test    ebx, ebx
0x180053bb1  jz      loc_180055358
0x180053bb7  test    rsi, rsi
0x180053bba  jz      loc_180055358
0x180053bc0  jmp     loc_18005506D
0x180053bc5  mov     rcx, [r15+8]
0x180053bc9  test    rcx, rcx
0x180053bcc  jz      short loc_180053B75
0x180053bce  mov     rax, r12
0x180053bd1  inc     rax
0x180053bd4  cmp     [rcx+rax*2], r9w
0x180053bd9  jnz     short loc_180053BD1
0x180053bdb  cmp     rax, 100h
0x180053be1  jnb     short loc_180053B75
0x180053be3  jmp     loc_180053B0D
0x180053be8  lea     rdx, [rsp+1B0h+var_13C]; int *
0x180053bed  mov     ecx, ebx; unsigned int
0x180053bef  call    ?AcmIsActiveConsoleSession@@YAKKPEAH@Z; AcmIsActiveConsoleSession(ulong,int *)
0x180053bf4  mov     ebx, eax
0x180053bf6  test    eax, eax
0x180053bf8  jz      short loc_180053C2F
0x180053bfa  mov     rdi, cs:WPP_GLOBAL_Control
0x180053c01  lea     r12, WPP_GLOBAL_Control
0x180053c08  cmp     rdi, r12
0x180053c0b  jz      loc_180055358
0x180053c11  cmp     byte ptr [rdi+69h], 1
0x180053c15  jb      loc_180055358
0x180053c1b  test    byte ptr [rdi+6Ch], 1
0x180053c1f  jz      loc_180055358
0x180053c25  mov     edx, 0A7h
0x180053c2a  jmp     loc_180053D8E
0x180053c2f  lea     rax, [rsp+1B0h+var_150]
0x180053c34  mov     [rsp+1B0h+var_188], rax
0x180053c39  mov     dword ptr [rsp+1B0h+var_190], 1
0x180053c41  xor     r9d, r9d
0x180053c44  mov     r8d, 494E5446h
0x180053c4a  mov     rdx, [rbp+0B0h+var_128]
0x180053c4e  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180053c55  call    cs:__imp_HtReferenceHandleWithTag
0x180053c5b  mov     ebx, eax
0x180053c5d  test    eax, eax
0x180053c5f  jz      short loc_180053C96
0x180053c61  mov     rdi, cs:WPP_GLOBAL_Control
0x180053c68  lea     r12, WPP_GLOBAL_Control
0x180053c6f  cmp     rdi, r12
0x180053c72  jz      loc_180055358
0x180053c78  cmp     byte ptr [rdi+69h], 1
0x180053c7c  jb      loc_180055358
0x180053c82  test    byte ptr [rdi+6Ch], 1
0x180053c86  jz      loc_180055358
0x180053c8c  mov     edx, 0A8h
0x180053c91  jmp     loc_180053D8E
0x180053c96  mov     rax, [rsp+1B0h+var_150]
0x180053c9b  cmp     dword ptr [rax+18h], 4
0x180053c9f  jnz     short loc_180053CFB
0x180053ca1  mov     eax, [r15]
0x180053ca4  sub     eax, 2
0x180053ca7  cmp     eax, 1
0x180053caa  ja      short loc_180053CFB
0x180053cac  mov     ebx, 32h ; '2'
0x180053cb1  mov     rdi, cs:WPP_GLOBAL_Control
0x180053cb8  lea     r12, WPP_GLOBAL_Control
0x180053cbf  cmp     rdi, r12
0x180053cc2  jz      loc_180055358
0x180053cc8  cmp     byte ptr [rdi+69h], 1
0x180053ccc  jb      loc_180055358
0x180053cd2  test    byte ptr [rdi+6Ch], 1
0x180053cd6  jz      loc_180055358
0x180053cdc  lea     edx, [rbx+77h]
0x180053cdf  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x180053ce6  mov     rcx, [rdi+60h]
0x180053cea  call    WPP_SF_
0x180053cef  mov     rdi, cs:WPP_GLOBAL_Control
0x180053cf6  jmp     loc_180055358
0x180053cfb  mov     edi, [rsp+1B0h+var_13C]
0x180053cff  mov     r8d, edi; int
0x180053d02  mov     rdx, [rsp+1B0h+var_150]; struct _WLAN_INTERFACE_CONTEXT *
0x180053d07  mov     ecx, esi; unsigned int
0x180053d09  call    ?IntfCheckDisconnectPrivilege@@YAKKPEAU_WLAN_INTERFACE_CONTEXT@@H@Z; IntfCheckDisconnectPrivilege(ulong,_WLAN_INTERFACE_CONTEXT *,int)
0x180053d0e  mov     ebx, eax
0x180053d10  test    eax, eax
0x180053d12  jz      short loc_180053D46
0x180053d14  mov     rdi, cs:WPP_GLOBAL_Control
0x180053d1b  lea     r12, WPP_GLOBAL_Control
0x180053d22  cmp     rdi, r12
0x180053d25  jz      loc_180055358
0x180053d2b  cmp     byte ptr [rdi+69h], 1
0x180053d2f  jb      loc_180055358
0x180053d35  test    byte ptr [rdi+6Ch], 1
0x180053d39  jz      loc_180055358
0x180053d3f  mov     edx, 0AAh
0x180053d44  jmp     short loc_180053D8E
0x180053d46  mov     r9d, edi; int
0x180053d49  mov     r8, r15; struct _WLAN_CONNECTION_PARAMETERS_V2 *
0x180053d4c  mov     rdx, [rsp+1B0h+var_150]; struct _WLAN_INTERFACE_CONTEXT *
0x180053d51  mov     ecx, esi; unsigned int
0x180053d53  call    ?IntfCheckConnectPrivilege@@YAKKPEAU_WLAN_INTERFACE_CONTEXT@@PEAU_WLAN_CONNECTION_PARAMETERS_V2@@H@Z; IntfCheckConnectPrivilege(ulong,_WLAN_INTERFACE_CONTEXT *,_WLAN_CONNECTION_PARAMETERS_V2 *,int)
0x180053d58  mov     ebx, eax
0x180053d5a  test    eax, eax
0x180053d5c  jz      short loc_180053D96
0x180053d5e  mov     rdi, cs:WPP_GLOBAL_Control
0x180053d65  lea     r12, WPP_GLOBAL_Control
0x180053d6c  cmp     rdi, r12
0x180053d6f  jz      loc_180055358
0x180053d75  cmp     byte ptr [rdi+69h], 1
0x180053d79  jb      loc_180055358
0x180053d7f  test    byte ptr [rdi+6Ch], 1
0x180053d83  jz      loc_180055358
0x180053d89  mov     edx, 0ABh
0x180053d8e  mov     r9d, eax
0x180053d91  jmp     loc_180053FD6
0x180053d96  mov     rdx, [rsp+1B0h+var_150]
0x180053d9b  add     rdx, 8
0x180053d9f  lea     rcx, [rsp+1B0h+var_148]
0x180053da4  call    ?Wim11adGetRefPairedInterfaceContext@@YA?AV?$unique_ptr@U_WLAN_INTERFACE_CONTEXT@@Uintfctxt_dereferencer@wlansvc@@@wistd@@AEBU_GUID@@@Z; Wim11adGetRefPairedInterfaceContext(_GUID const &)
0x180053da9  nop
0x180053daa  mov     rdx, qword ptr [rsp+1B0h+var_148.OILength]; struct _WLAN_INTERFACE_CONTEXT *
0x180053daf  xor     ebx, ebx
0x180053db1  test    rdx, rdx
0x180053db4  jz      short loc_180053E28
0x180053db6  mov     rax, [rsp+1B0h+var_150]
0x180053dbb  mov     eax, [rax+2A8h]
0x180053dc1  test    eax, eax
0x180053dc3  jz      short loc_180053E28
0x180053dc5  add     eax, 0FFFFFFFDh
0x180053dc8  cmp     eax, 1
0x180053dcb  jbe     short loc_180053E28
0x180053dcd  mov     r8d, edi; int
0x180053dd0  mov     ecx, esi; unsigned int
0x180053dd2  call    ?IntfCheckDisconnectPrivilege@@YAKKPEAU_WLAN_INTERFACE_CONTEXT@@H@Z; IntfCheckDisconnectPrivilege(ulong,_WLAN_INTERFACE_CONTEXT *,int)
0x180053dd7  mov     ebx, eax
0x180053dd9  test    eax, eax
0x180053ddb  jz      short loc_180053E26
0x180053ddd  mov     rcx, cs:WPP_GLOBAL_Control
0x180053de4  lea     r12, WPP_GLOBAL_Control
0x180053deb  cmp     rcx, r12
0x180053dee  jz      short loc_180053E15
0x180053df0  cmp     byte ptr [rcx+69h], 1
0x180053df4  jb      short loc_180053E15
0x180053df6  test    byte ptr [rcx+6Ch], 1
0x180053dfa  jz      short loc_180053E15
0x180053dfc  mov     edx, 0ACh
0x180053e01  mov     r9d, eax
0x180053e04  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x180053e0b  mov     rcx, [rcx+60h]
0x180053e0f  call    WPP_SF_d
0x180053e14  nop
0x180053e15  xor     edx, edx
0x180053e17  lea     rcx, [rsp+1B0h+var_148]
0x180053e1c  call    ?reset@?$unique_ptr@U_WLAN_INTERFACE_CONTEXT@@Uintfctxt_dereferencer@wlansvc@@@wistd@@QEAAXPEAU_WLAN_INTERFACE_CONTEXT@@@Z; wistd::unique_ptr<_WLAN_INTERFACE_CONTEXT,wlansvc::intfctxt_dereferencer>::reset(_WLAN_INTERFACE_CONTEXT *)
0x180053e21  jmp     loc_180053CEF
0x180053e26  xor     ebx, ebx
0x180053e28  xor     edx, edx
0x180053e2a  lea     rcx, [rsp+1B0h+var_148]
0x180053e2f  call    ?reset@?$unique_ptr@U_WLAN_INTERFACE_CONTEXT@@Uintfctxt_dereferencer@wlansvc@@@wistd@@QEAAXPEAU_WLAN_INTERFACE_CONTEXT@@@Z; wistd::unique_ptr<_WLAN_INTERFACE_CONTEXT,wlansvc::intfctxt_dereferencer>::reset(_WLAN_INTERFACE_CONTEXT *)
0x180053e34  mov     r9, [r15+20h]
0x180053e38  test    r9, r9
0x180053e3b  jz      loc_180053EF0
0x180053e41  mov     eax, [r9+8]
0x180053e45  mov     r9d, [r9+4]
0x180053e49  cmp     r9d, eax
0x180053e4c  jbe     short loc_180053E97
0x180053e4e  mov     rdi, cs:WPP_GLOBAL_Control
0x180053e55  lea     r12, WPP_GLOBAL_Control
0x180053e5c  cmp     rdi, r12
0x180053e5f  jz      loc_180053B52
0x180053e65  cmp     byte ptr [rdi+69h], 1
0x180053e69  jb      loc_180053B52
  ... truncated ...
```
