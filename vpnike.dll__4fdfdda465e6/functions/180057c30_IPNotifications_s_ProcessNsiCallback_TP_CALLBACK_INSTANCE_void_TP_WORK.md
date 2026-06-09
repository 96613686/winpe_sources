# IPNotifications::s_ProcessNsiCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180057c30`
- end: `0x1800587a6`
- name: `?s_ProcessNsiCallback@IPNotifications@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `2934`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001564`
- `0x180002cf8`
- `0x180006698`
- `0x180006738`
- `0x180007070`
- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x18000a3a0`
- `0x180057b48`
- `0x180057b74`
- `0x180057c30`
- `0x1800587ac`
- `0x18005d9ac`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180057e1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180057e1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057e11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057e11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057d63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057ed7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057f8e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800585d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057d63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057ed7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057f8e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800585d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057dae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057e28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057f31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005813b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800584b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800585b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058600`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800586a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057dae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057e28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057f31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005813b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800584b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800585b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058600`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800586a7`
- `IPHLPAPI!GetUnicastIpAddressEntry` at `0x18005829f`
- `IPHLPAPI!GetUnicastIpAddressEntry` at `0x18005829f`
- `IPHLPAPI!GetIfEntry2` at `0x1800580c6`
- `IPHLPAPI!GetIfEntry2` at `0x18005831d`
- `IPHLPAPI!GetIfEntry2` at `0x1800580c6`
- `IPHLPAPI!GetIfEntry2` at `0x18005831d`

## string_xrefs

- `0x180058077`: `IPChange notification:Index[%u]:IPAddress:[%S]. Determine whether interface Delete or not`
- `0x180058203`: `IPChange notification:Index[%u]:IPAddress:[%S]:Interface DELETED.`
- `0x180058124`: `Trying to update the interface`
- `0x18005843d`: `DELETE`
- `0x18005845b`: `IP Address: [%S] moved from [%s] to [%s] wish list`
- `0x180058664`: `Delete`
- `0x1800584cb`: `Protocol Engine is not initialize`

## pseudocode

```c
void __fastcall IPNotifications::s_ProcessNsiCallback(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WORK Work)
{
  PVOID v4; // rcx
  _QWORD *v5; // rbx
  PVOID *v6; // rcx
  __int64 v7; // rdx
  _QWORD *v8; // rcx
  char *v9; // rax
  __int64 v10; // rdx
  char *v11; // rdi
  __m128i v12; // xmm7
  __int128 v13; // xmm8
  __m128i v14; // xmm6
  __int128 v15; // xmm9
  __int128 v16; // xmm10
  int v17; // r14d
  HANDLE ProcessHeap; // rax
  unsigned int v19; // r15d
  VPNIKEProtocolEngine *v20; // rcx
  struct _RTL_CRITICAL_SECTION *v21; // rsi
  VPNIKEProtocolEngine *v22; // rcx
  unsigned __int8 v23; // r15
  const SOCKADDR **i; // rsi
  const SOCKADDR *v25; // rcx
  unsigned int IfEntry2; // eax
  __int64 *v27; // rdx
  VPNIKEProtocolEngine *v28; // rcx
  const wchar_t *v29; // rdx
  __int64 v30; // rcx
  unsigned int UnicastIpAddressEntry; // eax
  const SOCKADDR **j; // r8
  const SOCKADDR *v33; // rsi
  __int64 v34; // r8
  const wchar_t *v35; // r9
  const wchar_t *v36; // rax
  __int64 v37; // rdx
  char *v38; // rcx
  VPNIKEProtocolEngine *v39; // rcx
  __int64 k; // r14
  unsigned int *v41; // rdi
  unsigned int v42; // r12d
  __int64 v43; // r14
  struct _RTL_CRITICAL_SECTION *v44; // rsi
  _QWORD **v45; // rcx
  const char *v46; // r8
  _QWORD *v47; // rcx
  _QWORD *v48; // rdi
  __int64 v49; // [rsp+28h] [rbp-E0h]
  char v50; // [rsp+38h] [rbp-D0h]
  unsigned int v51; // [rsp+3Ch] [rbp-CCh]
  __int16 v52; // [rsp+40h] [rbp-C8h]
  char *v53; // [rsp+48h] [rbp-C0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-B8h]
  __int64 v55; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD *v56; // [rsp+60h] [rbp-A8h]
  __int64 v57; // [rsp+68h] [rbp-A0h]
  _OWORD v58[2]; // [rsp+70h] [rbp-98h] BYREF
  _MIB_UNICASTIPADDRESS_ROW v59; // [rsp+98h] [rbp-70h] BYREF
  SOCKADDR b; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v61; // [rsp+F8h] [rbp-10h]
  __m128i v62; // [rsp+108h] [rbp+0h]
  __int128 v63; // [rsp+118h] [rbp+10h]
  __int128 v64; // [rsp+128h] [rbp+20h]
  _MIB_IF_ROW2 Row; // [rsp+138h] [rbp+30h] BYREF
  int v66; // [rsp+688h] [rbp+580h] BYREF
  char v67[2044]; // [rsp+68Ch] [rbp+584h] BYREF

  v53 = Context;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
  }
  v5 = (_QWORD *)std::list<VPNIKEConnection *>::_Buynode(v4, Context, Work);
  v56 = v5;
  v57 = 0;
  memset(v58, 0, 28);
  v59.Address.Ipv4.sin_family = 0;
  *((_DWORD *)&v59.Address + 7) = 0;
  memset_0(&v59.Address.Ipv6.sin6_port, 0, 0x4Eu);
  v66 = 0;
  memset_0(v67, 0, sizeof(v67));
  if ( !Context )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 31;
LABEL_10:
      WPP_SF_(v6[2], v7, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
LABEL_145:
      v6 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_146;
    }
    goto LABEL_146;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 88));
  v8 = Context + 136;
  v9 = (char *)*((_QWORD *)Context + 17);
  if ( v9 == Context + 136 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 88));
    goto LABEL_145;
  }
  if ( *((_QWORD **)v9 + 1) != v8 || (v10 = *(_QWORD *)v9, *(char **)(*(_QWORD *)v9 + 8LL) != v9) )
    __fastfail(3u);
  *v8 = v10;
  *(_QWORD *)(v10 + 8) = v8;
  v11 = v9 - 88;
  v12 = *(__m128i *)(v9 - 88);
  b = (SOCKADDR)v12;
  v13 = *(_OWORD *)(v9 - 72);
  v61 = v13;
  v14 = *(__m128i *)(v9 - 56);
  v62 = v14;
  v15 = *(_OWORD *)(v9 - 40);
  v63 = v15;
  v16 = *(_OWORD *)(v9 - 24);
  v64 = v16;
  v17 = *((_DWORD *)v9 - 2);
  if ( v9 != (char *)88 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v11);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 88));
  v19 = _mm_cvtsi128_si32(_mm_srli_si128(v14, 8));
  v51 = v19;
  v20 = (VPNIKEProtocolEngine *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids, v19, v17);
    v20 = (VPNIKEProtocolEngine *)WPP_GLOBAL_Control;
  }
  if ( VpnIkeProtocolEngine )
  {
    VPNIKEProtocolEngine::AddRefAllActiveConnections(v20);
    v50 = 1;
  }
  else
  {
    v50 = 0;
    if ( v20 != (VPNIKEProtocolEngine *)&WPP_GLOBAL_Control
      && (*((_BYTE *)v20 + 28) & 1) != 0
      && *((_BYTE *)v20 + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)v20 + 2), 34, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
    }
  }
  v21 = (struct _RTL_CRITICAL_SECTION *)(Context + 32);
  lpCriticalSection = (LPCRITICAL_SECTION)(Context + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 32));
  v52 = _mm_cvtsi128_si32(v12);
  if ( v17 == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids, v19);
    }
    LeaveCriticalSection(v21);
    if ( VpnIkeProtocolEngine )
    {
      VPNIKEProtocolEngine::UpdateInterface(v22, v19, v52 == 2);
      v23 = 1;
    }
    else
    {
      v23 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
      }
    }
    EnterCriticalSection(v21);
  }
  else
  {
    if ( v17 != 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
      }
      for ( i = (const SOCKADDR **)(v53 + 16); ; i = (const SOCKADDR **)&v25[70].sa_data[6] )
      {
        v25 = *i;
        if ( !*i )
        {
          for ( i = (const SOCKADDR **)(v53 + 24); *i; i = (const SOCKADDR **)(v30 + 1128) )
          {
            if ( INETADDR_ISEQUAL(*i, &b) )
            {
              if ( (byte_1800AA941 & 8) != 0 )
              {
                LOWORD(v66) = 0;
                FormatRRASErrorString(
                  &v66,
                  L"IPChange notification:Index[%u]:IPAddress:[%S]. Determine whether interface Add or not",
                  v19,
                  &(*i)[2]);
                if ( (byte_1800AA941 & 8) != 0 )
                  McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v66);
              }
              v59.Address.Ipv4 = (SOCKADDR_IN)v12;
              *((_OWORD *)&v59.Address.si_family + 1) = v13;
              *(__m128i *)&v59.InterfaceLuid.Value = v14;
              *(_OWORD *)&v59.SuffixOrigin = v15;
              *(_OWORD *)&v59.DadState = v16;
              UnicastIpAddressEntry = GetUnicastIpAddressEntry(&v59);
              if ( UnicastIpAddressEntry )
              {
                if ( (byte_1800AA941 & 8) != 0 )
                {
                  LOWORD(v66) = 0;
                  FormatRRASErrorString(
                    &v66,
                    L"IPChange notification:GetUnicastIpAddressEntry failed: %d",
                    UnicastIpAddressEntry);
                  if ( (byte_1800AA941 & 8) != 0 )
                  {
                    v27 = RasVpnIkeTraceInfo;
                    goto LABEL_65;
                  }
                }
                goto LABEL_68;
              }
              if ( v59.DadState == NldsPreferred || v59.DadState == NldsTentative )
              {
                Row.InterfaceLuid.Value = 0;
                memset_0(&Row.InterfaceIndex, 0, 0x540u);
                Row.InterfaceIndex = v59.InterfaceIndex;
                IfEntry2 = GetIfEntry2(&Row);
                if ( IfEntry2 )
                  goto LABEL_62;
                if ( (byte_1800AA941 & 8) != 0 )
                {
                  LOWORD(v66) = 0;
                  LODWORD(v49) = Row.MediaConnectState;
                  FormatRRASErrorString(
                    &v66,
                    L"IPChange notification:Index[%u]:OperStatus[%u]:MediaStaus[%u]",
                    Row.InterfaceIndex,
                    (unsigned int)Row.OperStatus,
                    v49);
                  if ( (byte_1800AA941 & 8) != 0 )
                    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v66);
                }
                if ( Row.OperStatus == IfOperStatusUp )
                {
                  if ( (byte_1800AA941 & 8) == 0 )
                    goto LABEL_101;
                  v29 = L"IPChange notification:Index[%u]:IPAddress:[%S]:Interface ADDED.";
                  goto LABEL_99;
                }
              }
              goto LABEL_66;
            }
          }
          goto LABEL_66;
        }
        if ( v19 == *(_DWORD *)&v25[1].sa_data[10] && INETADDR_ISEQUAL(v25, &b) )
          break;
      }
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v66) = 0;
        FormatRRASErrorString(
          &v66,
          L"IPChange notification:Index[%u]:IPAddress:[%S]. Determine whether interface Delete or not",
          v19,
          &(*i)[2]);
        if ( (byte_1800AA941 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v66);
      }
      Row.InterfaceLuid.Value = 0;
      memset_0(&Row.InterfaceIndex, 0, 0x540u);
      Row.InterfaceIndex = v19;
      IfEntry2 = GetIfEntry2(&Row);
      if ( IfEntry2 )
      {
LABEL_62:
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v66) = 0;
          FormatRRASErrorString(&v66, L"IPChange notification:GetIfEntry2 failed: %d", IfEntry2);
          if ( (byte_1800AA941 & 4) != 0 )
          {
            v27 = RasVpnIkeTraceError;
LABEL_65:
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v27, &v66);
          }
        }
      }
      else
      {
        if ( (byte_1800AA941 & 8) != 0 )
        {
          LOWORD(v66) = 0;
          LODWORD(v49) = Row.MediaConnectState;
          FormatRRASErrorString(
            &v66,
            L"IPChange notification:Index[%u]:OperStatus[%u]:MediaStaus[%u]",
            Row.InterfaceIndex,
            (unsigned int)Row.OperStatus,
            v49);
          if ( (byte_1800AA941 & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v66);
        }
        if ( Row.OperStatus == IfOperStatusDown )
        {
          if ( (byte_1800AA941 & 8) != 0 )
          {
            v29 = L"IPChange notification:Index[%u]:IPAddress:[%S]:Interface DELETED.";
LABEL_99:
            LOWORD(v66) = 0;
            FormatRRASErrorString(&v66, v29, v19, &(*i)[2]);
            if ( (byte_1800AA941 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v66);
          }
          goto LABEL_101;
        }
      }
LABEL_66:
      if ( (byte_1800AA941 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasVpnIkeTraceInfo,
          L"Trying to update the interface");
LABEL_68:
      LeaveCriticalSection(lpCriticalSection);
      if ( VpnIkeProtocolEngine )
      {
        VPNIKEProtocolEngine::UpdateInterface(v28, v19, v52 == 2);
        goto LABEL_137;
      }
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
        goto LABEL_137;
      }
      goto LABEL_138;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
    }
LABEL_101:
    v23 = 0;
  }
  for ( j = (const SOCKADDR **)&v53[8 * v23 + 16]; ; j = (const SOCKADDR **)&v33[70].sa_data[6] )
  {
    v33 = *j;
    if ( !*j )
      break;
    if ( INETADDR_ISEQUAL(*j, &b) )
    {
      *(_DWORD *)&v33[1].sa_data[10] = v51;
      *(_QWORD *)v34 = *(_QWORD *)(*(_QWORD *)v34 + 1128LL);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v66) = 0;
        v35 = L"ADD";
        v36 = L"DELETE";
        if ( !v23 )
        {
          v36 = L"ADD";
          v35 = L"DELETE";
        }
        FormatRRASErrorString(&v66, L"IP Address: [%S] moved from [%s] to [%s] wish list", &v33[2], v35, v36);
        if ( (byte_1800AA941 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v66);
      }
      v37 = v23 ^ 1LL;
      v38 = v53;
      *(_QWORD *)&v33[70].sa_data[6] = *(_QWORD *)&v53[8 * v37 + 16];
      *(_QWORD *)&v38[8 * v37 + 16] = v33;
      v39 = VpnIkeProtocolEngine;
      if ( VpnIkeProtocolEngine )
      {
        for ( k = 0; (unsigned int)k < 0x80; k = (unsigned int)(k + 1) )
        {
          v41 = *(unsigned int **)&v33[6].sa_data[8 * k + 6];
          while ( v41 )
          {
            v53 = (char *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v39 + 1) + 40LL))(
                            *((_QWORD *)v39 + 1),
                            *(_QWORD *)v41);
            if ( v53 )
            {
              std::list<VPNIKEConnection *>::_Insert(&v55, v5, &v53);
              v5 = v56;
            }
            else if ( (byte_1800AA941 & 4) != 0 )
            {
              LOWORD(v66) = 0;
              FormatRRASErrorString(&v66, L"Unable to get VPNIKEConnection handle for ConnectionId: 0x%X", *v41);
              if ( (byte_1800AA941 & 4) != 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v66);
            }
            v41 = (unsigned int *)*((_QWORD *)v41 + 1);
            v39 = VpnIkeProtocolEngine;
          }
        }
        v58[0] = *v33;
        *(SOCKADDR *)((char *)v58 + 12) = *(SOCKADDR *)&v33->sa_data[10];
        v42 = *(_DWORD *)&v33[1].sa_data[10];
        LeaveCriticalSection(lpCriticalSection);
        v43 = v57;
        while ( v43 )
        {
          v44 = *(struct _RTL_CRITICAL_SECTION **)(*v5 + 16LL);
          EnterCriticalSection(v44 + 4);
          ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, _OWORD *, _QWORD, _QWORD))v44->DebugInfo[3].ProcessLocksList.Blink)(
            v44,
            v58,
            v42,
            (v23 ^ 1u) + 1);
          LeaveCriticalSection(v44 + 4);
          BaseConnection::DeleteRef((BaseConnection *)v44);
          v45 = (_QWORD **)*v5;
          if ( (_QWORD *)*v5 != v5 )
          {
            *v45[1] = *v45;
            (*v45)[1] = v45[1];
            operator delete(v45);
            v57 = --v43;
          }
        }
        VPNIKEProtocolEngine::RoamClientConnectionsToBestCostInterface(VpnIkeProtocolEngine);
      }
      else
      {
        LeaveCriticalSection(lpCriticalSection);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasVpnIkeTraceError,
            L"Protocol Engine is not initialize");
      }
      goto LABEL_137;
    }
  }
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v66) = 0;
    v46 = "Add";
    if ( !v23 )
      v46 = "Delete";
    FormatRRASErrorString(&v66, L"Ignoring IP%s notification:Index[%u]:IPAddress.", v46, v51);
    if ( (byte_1800AA941 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v66);
  }
  LeaveCriticalSection(lpCriticalSection);
LABEL_137:
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_138:
  if ( v50 )
  {
    if ( VpnIkeProtocolEngine )
    {
      VPNIKEProtocolEngine::ReleaseAllActiveConnections((VPNIKEProtocolEngine *)v6);
      goto LABEL_145;
    }
    if ( v6 == &WPP_GLOBAL_Control )
      goto LABEL_150;
    if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
    {
      v7 = 40;
      goto LABEL_10;
    }
  }
LABEL_146:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    WPP_SF_(v6[2], 41, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
LABEL_150:
  v47 = (_QWORD *)*v5;
  *v5 = v5;
  v5[1] = v5;
  if ( v47 != v5 )
  {
    do
    {
      v48 = (_QWORD *)*v47;
      operator delete(v47);
      v47 = v48;
    }
    while ( v48 != v5 );
  }
  operator delete(v5);
}

```

## disassembly

```asm
0x180057c30  mov     rax, rsp
0x180057c33  push    rbp
0x180057c34  push    rbx
0x180057c35  push    rsi
0x180057c36  push    rdi
0x180057c37  push    r12
0x180057c39  push    r13
0x180057c3b  push    r14
0x180057c3d  push    r15
0x180057c3f  lea     rbp, [rax-0E28h]
0x180057c46  sub     rsp, 0EE8h
0x180057c4d  movaps  xmmword ptr [rax-58h], xmm6
0x180057c51  movaps  xmmword ptr [rax-68h], xmm7
0x180057c55  movaps  xmmword ptr [rax-78h], xmm8
0x180057c5a  movaps  xmmword ptr [rax-88h], xmm9
0x180057c62  movaps  xmmword ptr [rax-98h], xmm10
0x180057c6a  mov     rax, cs:__security_cookie
0x180057c71  xor     rax, rsp
0x180057c74  mov     [rbp+0E20h+var_A0], rax
0x180057c7b  mov     r12, rdx
0x180057c7e  mov     [rsp+0F20h+var_EE0], rdx
0x180057c83  lea     r13, WPP_GLOBAL_Control
0x180057c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180057c91  cmp     rcx, r13
0x180057c94  jz      short loc_180057CB7
0x180057c96  test    byte ptr [rcx+1Ch], 1
0x180057c9a  jz      short loc_180057CB7
0x180057c9c  cmp     byte ptr [rcx+19h], 6
0x180057ca0  jb      short loc_180057CB7
0x180057ca2  mov     edx, 1Eh
0x180057ca7  lea     r8, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids
0x180057cae  mov     rcx, [rcx+10h]
0x180057cb2  call    WPP_SF_
0x180057cb7  call    ?_Buynode@?$list@PEAVVPNIKEConnection@@V?$allocator@PEAVVPNIKEConnection@@@std@@@std@@IEAAPEAU_Node@?$_List_nod@PEAVVPNIKEConnection@@V?$allocator@PEAVVPNIKEConnection@@@std@@@2@XZ; std::list<VPNIKEConnection *>::_Buynode(void)
0x180057cbc  mov     rbx, rax
0x180057cbf  mov     [rsp+0F20h+var_EC8], rax
0x180057cc4  mov     qword ptr [rsp+0F20h+var_EC0], 0
0x180057ccd  xor     eax, eax
0x180057ccf  mov     word ptr [rsp+0F20h+var_EC0+8], ax
0x180057cd4  xorps   xmm0, xmm0
0x180057cd7  movups  [rsp+0F20h+var_EC0+0Ah], xmm0
0x180057cdc  movups  [rsp+0F20h+var_EAC], xmm0
0x180057ce1  mov     word ptr [rbp+0E20h+var_E90.Address], ax
0x180057ce5  mov     dword ptr [rbp+0E20h+var_E90+1Ch], eax
0x180057ce8  xor     edx, edx; Val
0x180057cea  lea     r8d, [rax+4Eh]; Size
0x180057cee  lea     rcx, [rbp+0E20h+var_E90.Address+2]; void *
0x180057cf2  call    memset_0
0x180057cf7  xor     eax, eax
0x180057cf9  mov     [rbp+0E20h+var_8A0], eax
0x180057cff  xor     edx, edx; Val
0x180057d01  mov     r8d, 7FCh; Size
0x180057d07  lea     rcx, [rbp+0E20h+var_89C]; void *
0x180057d0e  call    memset_0
0x180057d13  test    r12, r12
0x180057d16  jnz     short loc_180057D5B
0x180057d18  mov     rcx, cs:WPP_GLOBAL_Control
0x180057d1f  cmp     rcx, r13
0x180057d22  jz      loc_18005870A
0x180057d28  test    byte ptr [rcx+1Ch], 1
0x180057d2c  jz      loc_18005870A
0x180057d32  lea     r13d, [r12+2]
0x180057d37  cmp     [rcx+19h], r13b
0x180057d3b  jb      loc_18005870A
0x180057d41  lea     edx, [r12+1Fh]
0x180057d46  lea     r8, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids
0x180057d4d  mov     rcx, [rcx+10h]
0x180057d51  call    WPP_SF_
0x180057d56  jmp     loc_180058703
0x180057d5b  lea     rsi, [r12+58h]
0x180057d60  mov     rcx, rsi; lpCriticalSection
0x180057d63  call    cs:__imp_EnterCriticalSection
0x180057d69  lea     rcx, [r12+88h]
0x180057d71  mov     rax, [rcx]
0x180057d74  cmp     rax, rcx
0x180057d77  jnz     short loc_180057DB9
0x180057d79  mov     rcx, cs:WPP_GLOBAL_Control
0x180057d80  cmp     rcx, r13
0x180057d83  jz      short loc_180057DAB
0x180057d85  test    byte ptr [rcx+1Ch], 1
0x180057d89  jz      short loc_180057DAB
0x180057d8b  mov     r13d, 2
0x180057d91  cmp     [rcx+19h], r13b
0x180057d95  jb      short loc_180057DAB
0x180057d97  lea     edx, [r13+1Eh]
0x180057d9b  lea     r8, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids
0x180057da2  mov     rcx, [rcx+10h]
0x180057da6  call    WPP_SF_
0x180057dab  mov     rcx, rsi; lpCriticalSection
0x180057dae  call    cs:__imp_LeaveCriticalSection
0x180057db4  jmp     loc_180058703
0x180057db9  cmp     [rax+8], rcx
0x180057dbd  jnz     loc_18005879F
0x180057dc3  mov     rdx, [rax]
0x180057dc6  cmp     [rdx+8], rax
0x180057dca  jnz     loc_18005879F
0x180057dd0  mov     [rcx], rdx
0x180057dd3  mov     [rdx+8], rcx
0x180057dd7  lea     rdi, [rax-58h]
0x180057ddb  movups  xmm7, xmmword ptr [rdi]
0x180057dde  movaps  xmmword ptr [rbp+0E20h+b.sa_family], xmm7
0x180057de2  movups  xmm8, xmmword ptr [rdi+10h]
0x180057de7  movaps  [rbp+0E20h+var_E30], xmm8
0x180057dec  movups  xmm6, xmmword ptr [rdi+20h]
0x180057df0  movaps  [rbp+0E20h+var_E20], xmm6
0x180057df4  movups  xmm9, xmmword ptr [rdi+30h]
0x180057df9  movaps  [rbp+0E20h+var_E10], xmm9
0x180057dfe  movups  xmm10, xmmword ptr [rdi+40h]
0x180057e03  movaps  [rbp+0E20h+var_E00], xmm10
0x180057e08  mov     r14d, [rdi+50h]
0x180057e0c  test    rdi, rdi
0x180057e0f  jz      short loc_180057E25
0x180057e11  call    cs:__imp_GetProcessHeap
0x180057e17  mov     rcx, rax; hHeap
0x180057e1a  mov     r8, rdi; lpMem
0x180057e1d  xor     edx, edx; dwFlags
0x180057e1f  call    cs:__imp_HeapFree
0x180057e25  mov     rcx, rsi; lpCriticalSection
0x180057e28  call    cs:__imp_LeaveCriticalSection
0x180057e2e  movdqa  xmm0, xmm6
0x180057e32  psrldq  xmm0, 8
0x180057e37  movd    r15d, xmm0
0x180057e3c  mov     [rsp+0F20h+var_EEC], r15d
0x180057e41  mov     rcx, cs:WPP_GLOBAL_Control
0x180057e48  cmp     rcx, r13
0x180057e4b  jz      short loc_180057E7D
0x180057e4d  test    byte ptr [rcx+1Ch], 1
0x180057e51  jz      short loc_180057E7D
0x180057e53  cmp     byte ptr [rcx+19h], 5
0x180057e57  jb      short loc_180057E7D
0x180057e59  mov     edx, 21h ; '!'
0x180057e5e  mov     dword ptr [rsp+0F20h+var_F00], r14d
0x180057e63  mov     r9d, r15d
0x180057e66  lea     r8, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids
0x180057e6d  mov     rcx, [rcx+10h]
0x180057e71  call    WPP_SF_dd
0x180057e76  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180057e7d  mov     r13d, 2
0x180057e83  cmp     cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA, 0; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180057e8b  jnz     short loc_180057EC0
0x180057e8d  mov     byte ptr [rsp+0F20h+var_EF0], 0
0x180057e92  lea     rax, WPP_GLOBAL_Control
0x180057e99  cmp     rcx, rax
0x180057e9c  jz      short loc_180057ECA
0x180057e9e  test    byte ptr [rcx+1Ch], 1
0x180057ea2  jz      short loc_180057ECA
0x180057ea4  cmp     [rcx+19h], r13b
0x180057ea8  jb      short loc_180057ECA
0x180057eaa  lea     edx, [r13+20h]
0x180057eae  lea     r8, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids
0x180057eb5  mov     rcx, [rcx+10h]
0x180057eb9  call    WPP_SF_
0x180057ebe  jmp     short loc_180057ECA
0x180057ec0  call    ?AddRefAllActiveConnections@VPNIKEProtocolEngine@@QEAAXXZ; VPNIKEProtocolEngine::AddRefAllActiveConnections(void)
0x180057ec5  mov     byte ptr [rsp+0F20h+var_EF0], 1
0x180057eca  lea     rsi, [r12+20h]
0x180057ecf  mov     [rsp+0F20h+lpCriticalSection], rsi
0x180057ed4  mov     rcx, rsi; lpCriticalSection
0x180057ed7  call    cs:__imp_EnterCriticalSection
0x180057edd  mov     dil, 8
0x180057ee0  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180057ee7  movd    dword ptr [rsp+0F20h+var_EE8], xmm7
0x180057eed  cmp     r14d, 1
0x180057ef1  jnz     loc_180057FA0
0x180057ef7  mov     rcx, cs:WPP_GLOBAL_Control
0x180057efe  lea     r14, WPP_GLOBAL_Control
0x180057f05  cmp     rcx, r14
0x180057f08  jz      short loc_180057F2E
0x180057f0a  test    byte ptr [rcx+1Ch], 1
0x180057f0e  jz      short loc_180057F2E
0x180057f10  cmp     byte ptr [rcx+19h], 5
0x180057f14  jb      short loc_180057F2E
0x180057f16  mov     edx, 23h ; '#'
0x180057f1b  mov     r9d, r15d
0x180057f1e  lea     r8, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids
0x180057f25  mov     rcx, [rcx+10h]
0x180057f29  call    WPP_SF_d
0x180057f2e  mov     rcx, rsi; lpCriticalSection
0x180057f31  call    cs:__imp_LeaveCriticalSection
0x180057f37  cmp     cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA, 0; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180057f3f  jnz     short loc_180057F73
0x180057f41  xor     r15b, r15b
0x180057f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180057f4b  cmp     rcx, r14
0x180057f4e  jz      short loc_180057F8B
0x180057f50  test    byte ptr [rcx+1Ch], 1
0x180057f54  jz      short loc_180057F8B
0x180057f56  cmp     [rcx+19h], r13b
0x180057f5a  jb      short loc_180057F8B
0x180057f5c  mov     edx, 24h ; '$'
0x180057f61  lea     r8, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids
0x180057f68  mov     rcx, [rcx+10h]
0x180057f6c  call    WPP_SF_
0x180057f71  jmp     short loc_180057F8B
0x180057f73  xor     r8d, r8d
0x180057f76  cmp     word ptr [rsp+0F20h+var_EE8], r13w
0x180057f7c  setz    r8b; int
0x180057f80  mov     edx, r15d; unsigned int
0x180057f83  call    ?UpdateInterface@VPNIKEProtocolEngine@@QEAAXKH@Z; VPNIKEProtocolEngine::UpdateInterface(ulong,int)
0x180057f88  mov     r15b, 1
0x180057f8b  mov     rcx, rsi; lpCriticalSection
0x180057f8e  call    cs:__imp_EnterCriticalSection
0x180057f94  lea     r14, RasVpnIkeTraceInfo
0x180057f9b  jmp     loc_1800583D8
0x180057fa0  cmp     r14d, r13d
0x180057fa3  jnz     short loc_180057FE5
0x180057fa5  mov     rcx, cs:WPP_GLOBAL_Control
0x180057fac  lea     rax, WPP_GLOBAL_Control
0x180057fb3  cmp     rcx, rax
0x180057fb6  jz      short loc_180057FD9
0x180057fb8  test    byte ptr [rcx+1Ch], 1
0x180057fbc  jz      short loc_180057FD9
0x180057fbe  cmp     byte ptr [rcx+19h], 5
0x180057fc2  jb      short loc_180057FD9
0x180057fc4  mov     edx, 25h ; '%'
0x180057fc9  lea     r8, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids
0x180057fd0  mov     rcx, [rcx+10h]
0x180057fd4  call    WPP_SF_
0x180057fd9  lea     r14, RasVpnIkeTraceInfo
0x180057fe0  jmp     loc_1800583D5
0x180057fe5  mov     rcx, cs:WPP_GLOBAL_Control
0x180057fec  lea     rax, WPP_GLOBAL_Control
0x180057ff3  cmp     rcx, rax
0x180057ff6  jz      short loc_180058019
0x180057ff8  test    byte ptr [rcx+1Ch], 1
0x180057ffc  jz      short loc_180058019
0x180057ffe  cmp     byte ptr [rcx+19h], 5
0x180058002  jb      short loc_180058019
0x180058004  mov     edx, 26h ; '&'
0x180058009  lea     r8, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids
0x180058010  mov     rcx, [rcx+10h]
0x180058014  call    WPP_SF_
0x180058019  mov     rsi, [rsp+0F20h+var_EE0]
0x18005801e  add     rsi, 10h
0x180058022  mov     rcx, [rsi]; a
0x180058025  mov     dil, 8
0x180058028  lea     r14, RasVpnIkeTraceInfo
0x18005802f  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180058036  test    rcx, rcx
0x180058039  jz      loc_18005820F
0x18005803f  cmp     r15d, [rcx+1Ch]
0x180058043  jnz     short loc_180058052
0x180058045  lea     rdx, [rbp+0E20h+b]; b
0x180058049  call    INETADDR_ISEQUAL
0x18005804e  test    al, al
0x180058050  jnz     short loc_18005805B
0x180058052  lea     rsi, [rcx+468h]
0x180058059  jmp     short loc_180058022
0x18005805b  test    cs:byte_1800AA941, dil
0x180058062  jz      short loc_1800580A5
0x180058064  xor     eax, eax
0x180058066  mov     word ptr [rbp+0E20h+var_8A0], ax
0x18005806d  mov     r9, [rsi]
0x180058070  add     r9, 20h ; ' '
0x180058074  mov     r8d, r15d
0x180058077  lea     rdx, aIpchangeNotifi_0; "IPChange notification:Index[%u]:IPAddre"...
0x18005807e  lea     rcx, [rbp+0E20h+var_8A0]
0x180058085  call    FormatRRASErrorString
0x18005808a  test    cs:byte_1800AA941, dil
0x180058091  jz      short loc_1800580A5
0x180058093  lea     r8, [rbp+0E20h+var_8A0]
0x18005809a  mov     rdx, r14
0x18005809d  mov     rcx, r12
0x1800580a0  call    McTemplateU0z_EventWriteTransfer
0x1800580a5  mov     qword ptr [rbp+0E20h+Row.InterfaceLuid], 0
0x1800580ad  xor     edx, edx; Val
0x1800580af  mov     r8d, 540h; Size
0x1800580b5  lea     rcx, [rbp+0E20h+Row.InterfaceIndex]; void *
0x1800580b9  call    memset_0
0x1800580be  mov     [rbp+0E20h+Row.InterfaceIndex], r15d
0x1800580c2  lea     rcx, [rbp+0E20h+Row]; Row
0x1800580c6  call    cs:__imp_GetIfEntry2
0x1800580cc  test    eax, eax
0x1800580ce  jz      loc_180058194
0x1800580d4  test    cs:byte_1800AA941, 4
0x1800580db  jz      short loc_18005811B
0x1800580dd  xor     ecx, ecx
0x1800580df  mov     word ptr [rbp+0E20h+var_8A0], cx
0x1800580e6  mov     r8d, eax
0x1800580e9  lea     rdx, aIpchangeNotifi_2; "IPChange notification:GetIfEntry2 faile"...
0x1800580f0  lea     rcx, [rbp+0E20h+var_8A0]
0x1800580f7  call    FormatRRASErrorString
0x1800580fc  test    cs:byte_1800AA941, 4
0x180058103  jz      short loc_18005811B
0x180058105  lea     rdx, RasVpnIkeTraceError
0x18005810c  lea     r8, [rbp+0E20h+var_8A0]
0x180058113  mov     rcx, r12
0x180058116  call    McTemplateU0z_EventWriteTransfer
0x18005811b  test    cs:byte_1800AA941, dil
0x180058122  jz      short loc_180058136
0x180058124  lea     r8, aTryingToUpdate; "Trying to update the interface"
0x18005812b  mov     rdx, r14
0x18005812e  mov     rcx, r12
0x180058131  call    McTemplateU0z_EventWriteTransfer
0x180058136  mov     rcx, [rsp+0F20h+lpCriticalSection]; lpCriticalSection
0x18005813b  call    cs:__imp_LeaveCriticalSection
0x180058141  cmp     cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA, 0; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180058149  jnz     loc_1800586AF
0x18005814f  mov     rcx, cs:WPP_GLOBAL_Control
0x180058156  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
