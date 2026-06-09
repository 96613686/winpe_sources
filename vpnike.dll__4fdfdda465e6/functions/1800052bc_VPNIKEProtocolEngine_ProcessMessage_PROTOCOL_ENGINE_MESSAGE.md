# VPNIKEProtocolEngine::ProcessMessage(_PROTOCOL_ENGINE_MESSAGE *)

- ea: `0x1800052bc`
- end: `0x180006691`
- name: `?ProcessMessage@VPNIKEProtocolEngine@@QEAAKPEAU_PROTOCOL_ENGINE_MESSAGE@@@Z`
- size: `5077`
- prototype: `__int64 __fastcall(VPNIKEProtocolEngine *this, struct _PROTOCOL_ENGINE_MESSAGE *)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800087d0`

## callees

- `0x180001514`
- `0x1800052bc`
- `0x180007590`
- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x1800077fc`
- `0x18000785c`
- `0x180007894`
- `0x180007a0c`
- `0x180023a6c`
- `0x18003a830`
- `0x18003ac84`
- `0x180040308`
- `0x180040454`
- `0x18005a92c`
- `0x18005b6d8`
- `0x18005b858`
- `0x18005d9ac`
- `0x180076ca0`
- `0x180076ccc`
- `0x180077552`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `ntdll!RtlIpv4AddressToStringW` at `0x18000638d`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000638d`
- `ntdll!RtlIpv6AddressToStringW` at `0x180006395`
- `ntdll!RtlIpv6AddressToStringW` at `0x180006395`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000624f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000624f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005405`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005405`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006241`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006241`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063c5`

## string_xrefs

- `0x1800057fa`: `VPNIKE is not configured to dial demand-dial connections`
- `0x18000587c`: `A connection object using same port (%I64u) already exists.`
- `0x180005ec4`: `A connection object using same port (%I64u) already exists.`
- `0x180005ba3`: `CreateConnection failed: %d`
- `0x180006078`: `CreateConnection failed: %d`
- `0x180005c11`: `Create trafficSelector failed: %d`
- `0x180005cd8`: `ThreadPool->QueueWorkItem failed: %d`
- `0x1800060e9`: `ThreadPool->QueueWorkItem failed: %d`
- `0x180006617`: `RemovePskPolicyForInterface failed: %d`
- `0x1800064e5`: `RemoveRDIkev2Policy failed: %d`

## pseudocode

```c
__int64 __fastcall VPNIKEProtocolEngine::ProcessMessage(
        VPNIKEProtocolEngine *this,
        struct _PROTOCOL_ENGINE_MESSAGE *a2)
{
  struct _PROTOCOL_ENGINE_MESSAGE *v2; // rdi
  unsigned int v3; // ebx
  HANDLE ProcessHeap; // rax
  _DWORD *v5; // rax
  _DWORD *v6; // r12
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  bool v11; // zf
  PVOID *v12; // rbx
  __int64 v13; // r9
  void *v14; // rax
  ConnectionParams *v15; // rsi
  VPNIKEProtocolEngine *v16; // rdi
  VPNIKEProtocolEngine *v17; // rsi
  _QWORD *v18; // r14
  void *v19; // rax
  ConnectionParams *v20; // rdi
  __int64 v21; // r8
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  HANDLE v25; // rax
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  HANDLE v34; // rax
  __int64 v36; // rax
  const struct in_addr *v37; // rax
  WCHAR *v38; // rdx
  const struct in_addr *v39; // rcx
  HANDLE v40; // rax
  __int64 *v41; // rax
  __int64 v42; // rcx
  const wchar_t *v43; // r8
  unsigned int v44; // eax
  const wchar_t *v45; // rdx
  size_t Size; // [rsp+48h] [rbp-990h]
  int v47; // [rsp+80h] [rbp-958h]
  BaseConnection *v49; // [rsp+90h] [rbp-948h] BYREF
  VPNIKEProtocolEngine *v50; // [rsp+98h] [rbp-940h]
  VPNIKEServerConnection *v51; // [rsp+A0h] [rbp-938h] BYREF
  ConnectionParams *v52; // [rsp+A8h] [rbp-930h]
  _DWORD *v53; // [rsp+B0h] [rbp-928h]
  _QWORD *v54; // [rsp+B8h] [rbp-920h]
  VPNIKEProtocolEngine *v55; // [rsp+C0h] [rbp-918h]
  char v56[8]; // [rsp+C8h] [rbp-910h] BYREF
  __int128 v57; // [rsp+D0h] [rbp-908h] BYREF
  int v58; // [rsp+E0h] [rbp-8F8h] BYREF
  __int128 v59; // [rsp+E4h] [rbp-8F4h]
  __int128 v60; // [rsp+F4h] [rbp-8E4h]
  int v61; // [rsp+104h] [rbp-8D4h]
  char v62; // [rsp+110h] [rbp-8C8h] BYREF
  char v63[143]; // [rsp+111h] [rbp-8C7h] BYREF
  int v64; // [rsp+1A0h] [rbp-838h] BYREF
  char v65[2044]; // [rsp+1A4h] [rbp-834h] BYREF

  v2 = a2;
  v50 = VpnIkeProtocolEngine;
  v55 = VpnIkeProtocolEngine;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
  }
  v64 = 0;
  memset_0(v65, 0, sizeof(v65));
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v57 = 0;
  v3 = 8;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v64) = 0;
    FormatRRASErrorString(&v64, L"VPNIKE Recevied message %S", (&szProtocolEngineMsg)[*(int *)v2]);
    if ( (byte_1800AA941 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v64);
  }
  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 8u, 0x1BE0u);
  v6 = v5;
  if ( !v5 )
    goto LABEL_169;
  v53 = v5;
  v3 = 0;
  memset_0(v5, 0, 0x1BE0u);
  memcpy_0(v6, v2, 0x1BE0u);
  v7 = *v6;
  if ( (int)*v6 <= 14 )
  {
    if ( v7 == 14 )
      goto LABEL_151;
    if ( v7 > 8 )
    {
      v22 = v7 - 10;
      if ( !v22 )
        goto LABEL_151;
      v23 = v22 - 1;
      if ( !v23 )
        goto LABEL_151;
      v24 = v23 - 1;
      if ( !v24 )
        goto LABEL_151;
      v11 = v24 == 1;
      goto LABEL_150;
    }
    if ( v7 != 8 )
    {
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( !v8 )
          goto LABEL_151;
        v9 = v8 - 2;
        if ( !v9 )
          goto LABEL_151;
        v10 = v9 - 1;
        if ( !v10 )
          goto LABEL_151;
        v11 = v10 == 2;
LABEL_150:
        if ( v11 )
        {
LABEL_151:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
          }
          v3 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(struct _TP_CALLBACK_INSTANCE *, char *, struct _TP_WORK *), _DWORD *, _QWORD))(**((_QWORD **)v50 + 3) + 16LL))(
                 *((_QWORD *)v50 + 3),
                 VPNIKEProtocolEngine::DispatchMessageA,
                 v6,
                 0);
          goto LABEL_156;
        }
LABEL_168:
        v34 = GetProcessHeap();
        HeapFree(v34, 0, v6);
        goto LABEL_169;
      }
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      v62 = 0;
      memset_0(v63, 0, 0x80u);
      v51 = 0;
      v49 = 0;
      if ( v12 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
        {
          WPP_SF_(v12[2], 25, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v12 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
          {
            WPP_SF_d(v12[2], 26, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, (unsigned int)v6[1026]);
            v12 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v12 != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
            {
              WPP_SF_q(v12[2], 27, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, *((_QWORD *)v6 + 514));
              v12 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v12 != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
              {
                WPP_SF_q(v12[2], 28, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, *((_QWORD *)v6 + 515));
                v12 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v12 != &WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
                {
                  WPP_SF__guid_(v12[2], 29, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, v6 + 1160);
                  v12 = (PVOID *)WPP_GLOBAL_Control;
                }
                if ( v12 != &WPP_GLOBAL_Control )
                {
                  if ( (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
                  {
                    WPP_SF_d(v12[2], 30, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, (unsigned int)v6[1458]);
                    v12 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  if ( v12 != &WPP_GLOBAL_Control )
                  {
                    if ( (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
                    {
                      WPP_SF_d(v12[2], 31, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, (unsigned int)v6[1164]);
                      v12 = (PVOID *)WPP_GLOBAL_Control;
                    }
                    if ( v12 != &WPP_GLOBAL_Control )
                    {
                      if ( (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
                      {
                        WPP_SF_d(v12[2], 32, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, (unsigned int)v6[1165]);
                        v12 = (PVOID *)WPP_GLOBAL_Control;
                      }
                      if ( v12 != &WPP_GLOBAL_Control )
                      {
                        if ( (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
                        {
                          LOBYTE(v13) = v6[1166] != 0;
                          WPP_SF_c(v12[2], 33, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, v13);
                          v12 = (PVOID *)WPP_GLOBAL_Control;
                        }
                        if ( v12 != &WPP_GLOBAL_Control )
                        {
                          if ( (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
                          {
                            LOBYTE(v13) = v6[1458] != 0;
                            WPP_SF_c(v12[2], 34, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, v13);
                            v12 = (PVOID *)WPP_GLOBAL_Control;
                          }
                          if ( v12 != &WPP_GLOBAL_Control )
                          {
                            if ( (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
                            {
                              WPP_SF_S(v12[2], 35, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, v6 + 1464);
                              v12 = (PVOID *)WPP_GLOBAL_Control;
                            }
                            if ( v12 != &WPP_GLOBAL_Control )
                            {
                              if ( (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
                              {
                                WPP_SF_S(
                                  v12[2],
                                  36,
                                  &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids,
                                  (char *)v6 + 6370);
                                v12 = (PVOID *)WPP_GLOBAL_Control;
                              }
                              if ( v12 != &WPP_GLOBAL_Control
                                && (*((_BYTE *)v12 + 28) & 1) != 0
                                && *((_BYTE *)v12 + 25) >= 5u )
                              {
                                LOBYTE(v13) = v6[1721] != 0;
                                WPP_SF_c(v12[2], 37, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, v13);
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      if ( (*((_BYTE *)v50 + 128) & 2) == 0 && v6[1026] == 2 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v58) = 0;
          ConvertPortNoToString(&v58, (unsigned int)v6[2]);
          if ( (byte_1800AA941 & 4) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)L"VPNIKE is not configured to dial demand-dial connections",
              (unsigned int)&v57,
              0,
              (__int64)&v58);
        }
        goto LABEL_79;
      }
      v49 = (BaseConnection *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v50 + 1) + 32LL))(
                                *((_QWORD *)v50 + 1),
                                *((_QWORD *)a2 + 1));
      if ( v49 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v64) = 0;
          LOWORD(v58) = 0;
          ConvertPortNoToString(&v58, (unsigned int)v6[2]);
          FormatRRASErrorString(
            &v64,
            L"A connection object using same port (%I64u) already exists.",
            *((_QWORD *)a2 + 1));
          if ( (byte_1800AA941 & 4) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v64,
              (unsigned int)&v57,
              0,
              (__int64)&v58);
        }
        v3 = 633;
        BaseConnection::DeleteRef(v49);
        goto LABEL_158;
      }
      v3 = (*(__int64 (__fastcall **)(VPNIKEProtocolEngine *, _QWORD, VPNIKEServerConnection **, char *))(*(_QWORD *)v50 + 40LL))(
             v50,
             *((_QWORD *)v6 + 1),
             &v51,
             &v62);
      if ( v3 )
      {
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_158;
        LOWORD(v64) = 0;
        LOWORD(v58) = 0;
        ConvertPortNoToString(&v58, (unsigned int)v6[2]);
        FormatRRASErrorString(&v64, L"GetRasDeviceParams failed: %d", v3);
LABEL_88:
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v64,
            (unsigned int)&v57,
            0,
            (__int64)&v58);
        goto LABEL_158;
      }
      try
      {
        v14 = operator new(0x1200u);
        if ( v14 )
          v52 = (ConnectionParams *)ConnectionParams::ConnectionParams(v14, 1, v51, *((_QWORD *)a2 + 1));
        else
          v52 = 0;
      }
      catch ( ... )
      {
        v3 = 14;
        v6 = v53;
        goto LABEL_158;
      }
      LODWORD(Size) = v6[1742];
      v15 = v52;
      v3 = ConnectionParams::SetConnectionParams(
             v52,
             *((void **)a2 + 2),
             (char *)v6 + 41,
             (char *)v6 + 301,
             &v62,
             (STRSAFE_LPCSTR)v6 + 1966,
             (STRSAFE_LPCSTR)v6 + 2223,
             (STRSAFE_LPCSTR)v6 + 2480,
             *((unsigned __int8 **)v6 + 870),
             Size,
             (char *)v6 + 3576,
             (struct _PROTOCOL_CFG_INFO *)(v6 + 626),
             (struct _GUID *)v6 + 434,
             *((void **)v6 + 862),
             (struct _PROTOCOL_INTERFACE_INFO *)(v6 + 1026),
             (struct _RAS_ADVCONNECTIONPARAMS *)(v6 + 1744));
      if ( v3 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v64) = 0;
          LOWORD(v58) = 0;
          ConvertPortNoToString(&v58, (unsigned int)v6[2]);
          FormatRRASErrorString(&v64, L"SetConnectionParams failed: %d", v3);
          if ( (byte_1800AA941 & 4) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v64,
              (unsigned int)&v57,
              0,
              (__int64)&v58);
        }
        if ( v15 )
          (**(void (__fastcall ***)(ConnectionParams *, __int64))v15)(v15, 1);
        goto LABEL_158;
      }
      v16 = v50;
      v3 = (*(__int64 (__fastcall **)(_QWORD, ConnectionParams *, BaseConnection **))(**((_QWORD **)v50 + 1) + 8LL))(
             *((_QWORD *)v50 + 1),
             v15,
             &v49);
      if ( v3 )
      {
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_158;
        LOWORD(v64) = 0;
        LOWORD(v58) = 0;
        ConvertPortNoToString(&v58, (unsigned int)v6[2]);
        FormatRRASErrorString(&v64, L"CreateConnection failed: %d", v3);
        goto LABEL_88;
      }
      BaseConnection::DeleteRef(v49);
      v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v49 + 26) + 16LL))(*((_QWORD *)v49 + 26));
      if ( v3 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v64) = 0;
          LOWORD(v58) = 0;
          ConvertPortNoToString(&v58, (unsigned int)v6[2]);
          FormatRRASErrorString(&v64, L"Create trafficSelector failed: %d", v3);
          if ( (byte_1800AA941 & 4) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v64,
              (unsigned int)&v57,
              0,
              (__int64)&v58);
        }
        (*(void (__fastcall **)(_QWORD, VPNIKEServerConnection *))(**((_QWORD **)v16 + 1) + 24LL))(
          *((_QWORD *)v16 + 1),
          v51);
        goto LABEL_158;
      }
      v3 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(struct _TP_CALLBACK_INSTANCE *, char *, struct _TP_WORK *), _DWORD *, _QWORD))(**((_QWORD **)v16 + 3) + 16LL))(
             *((_QWORD *)v16 + 3),
             VPNIKEProtocolEngine::DispatchMessageA,
             v6,
             0);
      if ( !v3 )
        goto LABEL_169;
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v64) = 0;
        LOWORD(v58) = 0;
        ConvertPortNoToString(&v58, (unsigned int)v6[2]);
        FormatRRASErrorString(&v64, L"ThreadPool->QueueWorkItem failed: %d", v3);
        goto LABEL_88;
      }
LABEL_158:
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v6);
      goto LABEL_169;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
      v2 = a2;
    }
    v49 = 0;
    v47 = 0;
    v51 = 0;
    v17 = v50;
    v18 = (_QWORD *)((char *)v50 + 8);
    v54 = (_QWORD *)((char *)v50 + 8);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v50 + 1) + 120LL))(*((_QWORD *)v50 + 1));
    v3 = (*(__int64 (__fastcall **)(VPNIKEProtocolEngine *, _QWORD, BaseConnection **, _QWORD))(*(_QWORD *)v17 + 40LL))(
           v17,
           *((_QWORD *)v2 + 1),
           &v49,
           0);
    if ( v3 )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v64) = 0;
        LOWORD(v58) = 0;
        ConvertPortNoToString(&v58, (unsigned int)v6[2]);
        FormatRRASErrorString(&v64, L"GetRasDeviceParams failed: %d  ", v3);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v64,
            (unsigned int)&v57,
            0,
            (__int64)&v58);
      }
      LODWORD(v52) = 0;
    }
    else
    {
      LODWORD(v52) = 1;
      LODWORD(v50) = 1;
      if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v18 + 104LL))(*v18, (unsigned int)v49) )
      {
        v3 = 668;
        goto LABEL_141;
      }
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v18 + 112LL))(*v18, (unsigned int)v49);
      v51 = (VPNIKEServerConnection *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v18 + 32LL))(
                                        *v18,
                                        *((_QWORD *)v2 + 1));
      if ( v51 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v64) = 0;
          LOWORD(v58) = 0;
          ConvertPortNoToString(&v58, (unsigned int)v6[2]);
          FormatRRASErrorString(
            &v64,
            L"A connection object using same port (%I64u) already exists.",
            *((_QWORD *)v2 + 1));
          if ( (byte_1800AA941 & 4) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v64,
              (unsigned int)&v57,
              0,
              (__int64)&v58);
        }
        v3 = 633;
        BaseConnection::DeleteRef(v51);
      }
      else
      {
        try
        {
          v19 = operator new(0x1200u);
          if ( v19 )
            v20 = (ConnectionParams *)ConnectionParams::ConnectionParams(v19, 2, v49, *((_QWORD *)v2 + 1));
          else
            v20 = 0;
        }
        catch ( ... )
        {
          v3 = 14;
          v6 = v53;
          LODWORD(v52) = (_DWORD)v50;
          v47 = 0;
          v17 = v55;
          v18 = v54;
          goto LABEL_141;
        }
        v3 = ConnectionParams::SetConnectionParams(
               v20,
               (struct _GUID *)(v6 + 398),
               (struct tagRASTUNNELENDPOINT *)(v6 + 388),
               (struct tagRASTUNNELENDPOINT *)(v6 + 393),
               (STRSAFE_LPCSTR)v6 + 28,
               *((_DWORD *)v17 + 24));
        if ( v3 )
        {
          if ( (byte_1800AA941 & 4) == 0 )
            goto LABEL_141;
          LOWORD(v64) = 0;
          LOWORD(v58) = 0;
          ConvertPortNoToString(&v58, (unsigned int)v6[2]);
          FormatRRASErrorString(&v64, L"SetConnectionParams(coId) %d  ", v3);
        }
        else
        {
          v3 = (*(__int64 (__fastcall **)(_QWORD, ConnectionParams *, VPNIKEServerConnection **))(*(_QWORD *)*v18 + 8LL))(
                 *v18,
                 v20,
                 &v51);
          if ( v3 )
          {
            if ( (byte_1800AA941 & 4) == 0 )
              goto LABEL_141;
            LOWORD(v64) = 0;
            LOWORD(v58) = 0;
            ConvertPortNoToString(&v58, (unsigned int)v6[2]);
            FormatRRASErrorString(&v64, L"CreateConnection failed: %d", v3);
          }
          else
          {
            BaseConnection::DeleteRef(v51);
            v47 = 1;
            v3 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(struct _TP_CALLBACK_INSTANCE *, char *, struct _TP_WORK *), _DWORD *, _QWORD))(**((_QWORD **)v17 + 3) + 16LL))(
                   *((_QWORD *)v17 + 3),
                   VPNIKEProtocolEngine::DispatchMessageA,
                   v6,
                   0);
            if ( !v3 || (byte_1800AA941 & 4) == 0 )
              goto LABEL_141;
            LOWORD(v64) = 0;
            LOWORD(v58) = 0;
            ConvertPortNoToString(&v58, (unsigned int)v6[2]);
            FormatRRASErrorString(&v64, L"ThreadPool->QueueWorkItem failed: %d", v3);
          }
        }
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v64,
            (unsigned int)&v57,
            0,
            (__int64)&v58);
      }
    }
LABEL_141:
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 128LL))(*v18);
    if ( v3 )
    {
      if ( v47 )
      {
        VPNIKEServerConnection::MarkStopPending(v51, v3);
        (*(void (__fastcall **)(_QWORD, BaseConnection *))(*(_QWORD *)*v18 + 24LL))(*v18, v49);
      }
      if ( (_DWORD)v52 )
      {
        LOBYTE(v21) = 1;
        (*(void (__fastcall **)(_QWORD, BaseConnection *, __int64))(**((_QWORD **)v17 + 13) + 32LL))(
          *((_QWORD *)v17 + 13),
          v49,
          v21);
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v17 + 5) + 8LL))(*((_QWORD *)v17 + 5), (unsigned int)v49);
      }
      goto LABEL_158;
    }
    goto LABEL_169;
  }
  v26 = v7 - 16;
  if ( !v26 )
    goto LABEL_151;
  v27 = v26 - 1;
  if ( !v27 )
    goto LABEL_151;
  v28 = v27 - 1;
  if ( !v28 )
    goto LABEL_151;
  v29 = v28 - 1;
  if ( !v29 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
    }
    if ( (*((_BYTE *)v50 + 128) & 2) != 0 )
    {
      v44 = ServerBFEHandler::AddPskPolicyForInterface((struct _PROTOCOL_IKEv2_PSK_POLICY_INFO *)(v6 + 6));
      v3 = v44;
      if ( !v44 )
        goto LABEL_168;
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_158;
      v45 = L"AddPolicyForInterface failed: %d";
      goto LABEL_204;
    }
    goto LABEL_211;
  }
  v30 = v29 - 1;
  if ( !v30 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
    }
    if ( (*((_BYTE *)v50 + 128) & 2) != 0 )
    {
      v44 = ServerBFEHandler::RemovePskPolicyForInterface((struct _PROTOCOL_IKEv2_PSK_POLICY_INFO *)(v6 + 6));
      v3 = v44;
      if ( !v44 )
        goto LABEL_168;
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_158;
      v45 = L"RemovePskPolicyForInterface failed: %d";
      goto LABEL_204;
    }
    goto LABEL_211;
  }
  v31 = v30 - 1;
  if ( !v31 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
    }
    if ( (*((_BYTE *)v50 + 128) & 2) != 0 )
    {
      v44 = ServerBFEHandler::AddRDIkev2Policy((struct _PROTOCOL_RD_IKEv2_POLICY_INFO *)(v6 + 6));
      v3 = v44;
      if ( !v44 )
        goto LABEL_168;
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_158;
      v45 = L"AddRDIkev2Policy failed: %d";
      goto LABEL_204;
    }
LABEL_211:
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_79;
    v43 = L"VPNIKE server is not initialized";
    goto LABEL_200;
  }
  v32 = v31 - 1;
  if ( !v32 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
    }
    if ( (*((_BYTE *)v50 + 128) & 2) == 0 )
    {
      if ( (byte_1800AA941 & 4) == 0 )
      {
LABEL_79:
        v3 = 956;
        goto LABEL_158;
      }
      v43 = L"PNIKE server is not initialized";
LABEL_200:
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, v43);
      goto LABEL_79;
    }
    v44 = ServerBFEHandler::RemoveRDIkev2Policy((struct _PROTOCOL_RD_IKEv2_POLICY_INFO *)(v6 + 6));
    v3 = v44;
    if ( !v44 )
      goto LABEL_168;
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_158;
    v45 = L"RemoveRDIkev2Policy failed: %d";
LABEL_204:
    LOWORD(v64) = 0;
    FormatRRASErrorString(&v64, v45, v44);
    if ( (byte_1800AA941 & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v64);
    goto LABEL_158;
  }
  v33 = v32 - 1;
  if ( !v33 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
      v2 = a2;
    }
    *((_QWORD *)v2 + 3) = 0;
    v41 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)v50 + 1) + 48LL))(
                       *((_QWORD *)v50 + 1),
                       v56);
    v42 = *v41;
    *((_QWORD *)a2 + 3) = *v41;
    if ( v42 )
      goto LABEL_168;
    v3 = 837;
    goto LABEL_158;
  }
  if ( v33 != 1 )
    goto LABEL_168;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
  }
  v36 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v50 + 1) + 32LL))(
          *((_QWORD *)v50 + 1),
          *((_QWORD *)v6 + 1));
  if ( v36 && (v37 = *(const struct in_addr **)(v36 + 112)) != 0 )
  {
    v38 = (WCHAR *)((char *)a2 + 24);
    v39 = v37 + 1067;
    if ( v37[1066].S_un.S_un_b.s_b1 == 2 )
      RtlIpv4AddressToStringW(v39, v38);
    else
      RtlIpv6AddressToStringW((const struct in6_addr *)v39, v38);
  }
  else
  {
    v3 = 635;
    if ( (byte_1800AA941 & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasVpnIkeTraceError,
        L"Error:Unable to get EPDG Address");
  }
  v40 = GetProcessHeap();
  HeapFree(v40, 0, v6);
  v6 = 0;
LABEL_156:
  if ( v3 && v6 )
    goto LABEL_158;
LABEL_169:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x1800052bc  mov     [rsp+arg_0], rbx
0x1800052c1  mov     [rsp+arg_10], rsi
0x1800052c6  push    rdi
0x1800052c7  push    r12
0x1800052c9  push    r13
0x1800052cb  push    r14
0x1800052cd  push    r15
0x1800052cf  sub     rsp, 9B0h
0x1800052d6  mov     rax, cs:__security_cookie
0x1800052dd  xor     rax, rsp
0x1800052e0  mov     [rsp+9D8h+var_38], rax
0x1800052e8  mov     rdi, rdx
0x1800052eb  mov     [rsp+9D8h+var_950], rdx
0x1800052f3  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x1800052fa  mov     [rsp+9D8h+var_940], rax
0x180005302  mov     [rsp+9D8h+var_918], rax
0x18000530a  lea     r14, WPP_GLOBAL_Control
0x180005311  mov     rcx, cs:WPP_GLOBAL_Control
0x180005318  mov     r13d, 1
0x18000531e  cmp     rcx, r14
0x180005321  jz      short loc_180005348
0x180005323  test    [rcx+1Ch], r13b
0x180005327  jz      short loc_180005348
0x180005329  lea     rsi, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x180005330  cmp     byte ptr [rcx+19h], 6
0x180005334  jb      short loc_18000534F
0x180005336  lea     edx, [r13+16h]
0x18000533a  mov     r8, rsi
0x18000533d  mov     rcx, [rcx+10h]
0x180005341  call    WPP_SF_
0x180005346  jmp     short loc_18000534F
0x180005348  lea     rsi, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x18000534f  xor     r15d, r15d
0x180005352  mov     [rsp+9D8h+var_838], r15d
0x18000535a  xor     edx, edx; Val
0x18000535c  mov     r8d, 7FCh; Size
0x180005362  lea     rcx, [rsp+9D8h+var_834]; void *
0x18000536a  call    memset_0
0x18000536f  mov     [rsp+9D8h+var_8F8], r15d
0x180005377  xorps   xmm0, xmm0
0x18000537a  xor     eax, eax
0x18000537c  movups  [rsp+9D8h+var_8F4], xmm0
0x180005384  movups  [rsp+9D8h+var_8E4], xmm0
0x18000538c  mov     [rsp+9D8h+var_8D4], eax
0x180005393  movups  [rsp+9D8h+var_908], xmm0
0x18000539b  lea     ebx, [rax+8]
0x18000539e  test    cs:byte_1800AA941, bl
0x1800053a4  jz      short loc_1800053F4
0x1800053a6  mov     word ptr [rsp+9D8h+var_838], r15w
0x1800053af  movsxd  r8, dword ptr [rdi]
0x1800053b2  lea     rax, ?szProtocolEngineMsg@@3PAPEBDA; char const * near * szProtocolEngineMsg
0x1800053b9  mov     r8, [rax+r8*8]
0x1800053bd  lea     rdx, aVpnikeRecevied; "VPNIKE Recevied message %S"
0x1800053c4  lea     rcx, [rsp+9D8h+var_838]
0x1800053cc  call    FormatRRASErrorString
0x1800053d1  test    cs:byte_1800AA941, bl
0x1800053d7  jz      short loc_1800053F4
0x1800053d9  lea     r8, [rsp+9D8h+var_838]
0x1800053e1  lea     rdx, RasVpnIkeTraceInfo
0x1800053e8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800053ef  call    McTemplateU0z_EventWriteTransfer
0x1800053f4  call    cs:__imp_GetProcessHeap
0x1800053fa  mov     rcx, rax; hHeap
0x1800053fd  mov     r8d, 1BE0h; dwBytes
0x180005403  mov     edx, ebx; dwFlags
0x180005405  call    cs:__imp_HeapAlloc
0x18000540b  mov     r12, rax
0x18000540e  test    rax, rax
0x180005411  jz      loc_1800062B4
0x180005417  mov     [rsp+9D8h+var_928], rax
0x18000541f  mov     ebx, r15d
0x180005422  xor     edx, edx; Val
0x180005424  mov     r8d, 1BE0h; Size
0x18000542a  mov     rcx, rax; void *
0x18000542d  call    memset_0
0x180005432  mov     r8d, 1BE0h; Size
0x180005438  mov     rdx, rdi; Src
0x18000543b  mov     rcx, r12; void *
0x18000543e  call    memcpy_0
0x180005443  mov     ecx, [r12]
0x180005447  cmp     ecx, 0Eh
0x18000544a  jg      loc_180006257
0x180005450  jz      loc_1800061DE
0x180005456  cmp     ecx, 8
0x180005459  jg      loc_1800061C6
0x18000545f  jz      loc_180005CFE
0x180005465  test    ecx, ecx
0x180005467  jz      short loc_18000548C
0x180005469  sub     ecx, 1
0x18000546c  jz      loc_1800061DE
0x180005472  sub     ecx, 2
0x180005475  jz      loc_1800061DE
0x18000547b  sub     ecx, 1
0x18000547e  jz      loc_1800061DE
0x180005484  cmp     ecx, 2
0x180005487  jmp     loc_1800061D8
0x18000548c  mov     rbx, cs:WPP_GLOBAL_Control
0x180005493  cmp     rbx, r14
0x180005496  jz      short loc_1800054C1
0x180005498  test    [rbx+1Ch], r13b
0x18000549c  jz      short loc_1800054C1
0x18000549e  mov     dil, 5
0x1800054a1  cmp     [rbx+19h], dil
0x1800054a5  jb      short loc_1800054C4
0x1800054a7  mov     edx, 18h
0x1800054ac  mov     r8, rsi
0x1800054af  mov     rcx, [rbx+10h]
0x1800054b3  call    WPP_SF_
0x1800054b8  mov     rbx, cs:WPP_GLOBAL_Control
0x1800054bf  jmp     short loc_1800054C4
0x1800054c1  mov     dil, 5
0x1800054c4  mov     [rsp+9D8h+var_8C8], r15b
0x1800054cc  xor     edx, edx; Val
0x1800054ce  mov     r8d, 80h; Size
0x1800054d4  lea     rcx, [rsp+9D8h+var_8C7]; void *
0x1800054dc  call    memset_0
0x1800054e1  mov     [rsp+9D8h+var_938], r15
0x1800054e9  mov     [rsp+9D8h+var_948], r15
0x1800054f1  cmp     rbx, r14
0x1800054f4  jz      loc_180005797
0x1800054fa  test    [rbx+1Ch], r13b
0x1800054fe  jz      short loc_18000551E
0x180005500  cmp     [rbx+19h], dil
0x180005504  jb      short loc_18000551E
0x180005506  mov     edx, 19h
0x18000550b  mov     r8, rsi
0x18000550e  mov     rcx, [rbx+10h]
0x180005512  call    WPP_SF_
0x180005517  mov     rbx, cs:WPP_GLOBAL_Control
0x18000551e  cmp     rbx, r14
0x180005521  jz      loc_180005797
0x180005527  test    [rbx+1Ch], r13b
0x18000552b  jz      short loc_180005553
0x18000552d  cmp     [rbx+19h], dil
0x180005531  jb      short loc_180005553
0x180005533  mov     edx, 1Ah
0x180005538  mov     r9d, [r12+1008h]
0x180005540  mov     r8, rsi
0x180005543  mov     rcx, [rbx+10h]
0x180005547  call    WPP_SF_d
0x18000554c  mov     rbx, cs:WPP_GLOBAL_Control
0x180005553  cmp     rbx, r14
0x180005556  jz      loc_180005797
0x18000555c  test    [rbx+1Ch], r13b
0x180005560  jz      short loc_180005588
0x180005562  cmp     [rbx+19h], dil
0x180005566  jb      short loc_180005588
0x180005568  mov     edx, 1Bh
0x18000556d  mov     r9, [r12+1010h]
0x180005575  mov     r8, rsi
0x180005578  mov     rcx, [rbx+10h]
0x18000557c  call    WPP_SF_q
0x180005581  mov     rbx, cs:WPP_GLOBAL_Control
0x180005588  cmp     rbx, r14
0x18000558b  jz      loc_180005797
0x180005591  test    [rbx+1Ch], r13b
0x180005595  jz      short loc_1800055BD
0x180005597  cmp     [rbx+19h], dil
0x18000559b  jb      short loc_1800055BD
0x18000559d  mov     edx, 1Ch
0x1800055a2  mov     r9, [r12+1018h]
0x1800055aa  mov     r8, rsi
0x1800055ad  mov     rcx, [rbx+10h]
0x1800055b1  call    WPP_SF_q
0x1800055b6  mov     rbx, cs:WPP_GLOBAL_Control
0x1800055bd  cmp     rbx, r14
0x1800055c0  jz      loc_180005797
0x1800055c6  test    [rbx+1Ch], r13b
0x1800055ca  jz      short loc_1800055F2
0x1800055cc  cmp     [rbx+19h], dil
0x1800055d0  jb      short loc_1800055F2
0x1800055d2  lea     r9, [r12+1220h]
0x1800055da  mov     edx, 1Dh
0x1800055df  mov     r8, rsi
0x1800055e2  mov     rcx, [rbx+10h]
0x1800055e6  call    WPP_SF__guid_
0x1800055eb  mov     rbx, cs:WPP_GLOBAL_Control
0x1800055f2  cmp     rbx, r14
0x1800055f5  jz      loc_180005797
0x1800055fb  test    [rbx+1Ch], r13b
0x1800055ff  jz      short loc_180005627
0x180005601  cmp     [rbx+19h], dil
0x180005605  jb      short loc_180005627
0x180005607  mov     edx, 1Eh
0x18000560c  mov     r9d, [r12+16C8h]
0x180005614  mov     r8, rsi
0x180005617  mov     rcx, [rbx+10h]
0x18000561b  call    WPP_SF_d
0x180005620  mov     rbx, cs:WPP_GLOBAL_Control
0x180005627  cmp     rbx, r14
0x18000562a  jz      loc_180005797
0x180005630  test    [rbx+1Ch], r13b
0x180005634  jz      short loc_18000565C
0x180005636  cmp     [rbx+19h], dil
0x18000563a  jb      short loc_18000565C
0x18000563c  mov     edx, 1Fh
0x180005641  mov     r9d, [r12+1230h]
0x180005649  mov     r8, rsi
0x18000564c  mov     rcx, [rbx+10h]
0x180005650  call    WPP_SF_d
0x180005655  mov     rbx, cs:WPP_GLOBAL_Control
0x18000565c  cmp     rbx, r14
0x18000565f  jz      loc_180005797
0x180005665  test    [rbx+1Ch], r13b
0x180005669  jz      short loc_180005691
0x18000566b  cmp     [rbx+19h], dil
0x18000566f  jb      short loc_180005691
0x180005671  mov     edx, 20h ; ' '
0x180005676  mov     r9d, [r12+1234h]
0x18000567e  mov     r8, rsi
0x180005681  mov     rcx, [rbx+10h]
0x180005685  call    WPP_SF_d
0x18000568a  mov     rbx, cs:WPP_GLOBAL_Control
0x180005691  cmp     rbx, r14
0x180005694  jz      loc_180005797
0x18000569a  test    [rbx+1Ch], r13b
0x18000569e  jz      short loc_1800056CA
0x1800056a0  cmp     [rbx+19h], dil
0x1800056a4  jb      short loc_1800056CA
0x1800056a6  cmp     [r12+1238h], r15d
0x1800056ae  setnz   r9b
0x1800056b2  mov     edx, 21h ; '!'
0x1800056b7  mov     r8, rsi
0x1800056ba  mov     rcx, [rbx+10h]
0x1800056be  call    WPP_SF_c
0x1800056c3  mov     rbx, cs:WPP_GLOBAL_Control
0x1800056ca  cmp     rbx, r14
0x1800056cd  jz      loc_180005797
0x1800056d3  test    [rbx+1Ch], r13b
0x1800056d7  jz      short loc_180005703
0x1800056d9  cmp     [rbx+19h], dil
0x1800056dd  jb      short loc_180005703
0x1800056df  cmp     [r12+16C8h], r15d
0x1800056e7  setnz   r9b
0x1800056eb  mov     edx, 22h ; '"'
0x1800056f0  mov     r8, rsi
0x1800056f3  mov     rcx, [rbx+10h]
0x1800056f7  call    WPP_SF_c
0x1800056fc  mov     rbx, cs:WPP_GLOBAL_Control
0x180005703  cmp     rbx, r14
0x180005706  jz      loc_180005797
0x18000570c  test    [rbx+1Ch], r13b
0x180005710  jz      short loc_180005738
0x180005712  cmp     [rbx+19h], dil
0x180005716  jb      short loc_180005738
0x180005718  lea     r9, [r12+16E0h]
0x180005720  mov     edx, 23h ; '#'
0x180005725  mov     r8, rsi
0x180005728  mov     rcx, [rbx+10h]
0x18000572c  call    WPP_SF_S
0x180005731  mov     rbx, cs:WPP_GLOBAL_Control
0x180005738  cmp     rbx, r14
0x18000573b  jz      short loc_180005797
0x18000573d  test    [rbx+1Ch], r13b
0x180005741  jz      short loc_180005769
0x180005743  cmp     [rbx+19h], dil
0x180005747  jb      short loc_180005769
0x180005749  lea     r9, [r12+18E2h]
0x180005751  mov     edx, 24h ; '$'
0x180005756  mov     r8, rsi
0x180005759  mov     rcx, [rbx+10h]
0x18000575d  call    WPP_SF_S
0x180005762  mov     rbx, cs:WPP_GLOBAL_Control
0x180005769  cmp     rbx, r14
0x18000576c  jz      short loc_180005797
0x18000576e  test    [rbx+1Ch], r13b
0x180005772  jz      short loc_180005797
0x180005774  cmp     [rbx+19h], dil
0x180005778  jb      short loc_180005797
0x18000577a  cmp     [r12+1AE4h], r15d
0x180005782  setnz   r9b
0x180005786  mov     edx, 25h ; '%'
0x18000578b  mov     r8, rsi
0x18000578e  mov     rcx, [rbx+10h]
0x180005792  call    WPP_SF_c
0x180005797  mov     rbx, [rsp+9D8h+var_940]
0x18000579f  test    byte ptr [rbx+80h], 2
0x1800057a6  jnz     short loc_18000581E
0x1800057a8  cmp     dword ptr [r12+1008h], 2
0x1800057b1  jnz     short loc_18000581E
0x1800057b3  test    cs:byte_1800AA941, 4
0x1800057ba  jz      short loc_180005814
0x1800057bc  mov     word ptr [rsp+9D8h+var_8F8], r15w
0x1800057c5  mov     edx, [r12+8]
0x1800057ca  lea     rcx, [rsp+9D8h+var_8F8]
0x1800057d2  call    ConvertPortNoToString
0x1800057d7  test    cs:byte_1800AA941, 4
0x1800057de  jz      short loc_180005814
0x1800057e0  lea     rax, [rsp+9D8h+var_8F8]
0x1800057e8  mov     [rsp+9D8h+var_9B0], rax
0x1800057ed  mov     [rsp+9D8h+pszSrc], r15
0x1800057f2  lea     r9, [rsp+9D8h+var_908]
0x1800057fa  lea     r8, aVpnikeIsNotCon; "VPNIKE is not configured to dial demand"...
0x180005801  lea     rdx, RasVpnIkeParamTraceError
0x180005808  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000580f  call    McTemplateU0zjzz_EventWriteTransfer
0x180005814  mov     ebx, 3BCh
0x180005819  jmp     loc_18000623A
0x18000581e  mov     rcx, [rbx+8]
0x180005822  mov     rax, [rcx]
  ... truncated ...
```
