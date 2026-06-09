# s_wscUpdateProductStatus

- ea: `0x180025520`
- end: `0x180026443`
- name: `s_wscUpdateProductStatus`
- size: `3875`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `37`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180002e30`
- `0x180003f80`
- `0x180005220`
- `0x1800070f0`
- `0x180008cc0`
- `0x180008e48`
- `0x1800093cc`
- `0x180015bf0`
- `0x180016ae8`
- `0x180018b60`
- `0x1800196e0`
- `0x180019850`
- `0x180019e00`
- `0x18001abb0`
- `0x18001b7f0`
- `0x18001b870`
- `0x18001b960`
- `0x18001c6dc`
- `0x18001c780`
- `0x18001fdd8`
- `0x1800202e8`
- `0x180022ad0`
- `0x18002400c`
- `0x180024370`
- `0x1800250c0`
- `0x180025520`
- `0x1800281c4`
- `0x180028618`
- `0x180029158`
- `0x180029e74`
- `0x1800305ec`
- `0x180031efc`
- `0x1800351ac`
- `0x180036878`
- `0x180039540`
- `0x18003fc30`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025d7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025d7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025d69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025d69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263a4`
- `RPCRT4!RpcRevertToSelf` at `0x1800256a8`
- `RPCRT4!RpcRevertToSelf` at `0x18002579f`
- `RPCRT4!RpcRevertToSelf` at `0x180025c6a`
- `RPCRT4!RpcRevertToSelf` at `0x1800261cd`
- `RPCRT4!RpcRevertToSelf` at `0x1800256a8`
- `RPCRT4!RpcRevertToSelf` at `0x18002579f`
- `RPCRT4!RpcRevertToSelf` at `0x180025c6a`
- `RPCRT4!RpcRevertToSelf` at `0x1800261cd`
- `RPCRT4!RpcImpersonateClient` at `0x180025681`
- `RPCRT4!RpcImpersonateClient` at `0x180025773`
- `RPCRT4!RpcImpersonateClient` at `0x180025a90`
- `RPCRT4!RpcImpersonateClient` at `0x180025c3c`
- `RPCRT4!RpcImpersonateClient` at `0x180025681`
- `RPCRT4!RpcImpersonateClient` at `0x180025773`
- `RPCRT4!RpcImpersonateClient` at `0x180025a90`
- `RPCRT4!RpcImpersonateClient` at `0x180025c3c`
- `RPCRT4!RpcRaiseException` at `0x180025acd`
- `RPCRT4!RpcRaiseException` at `0x180025acd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180025861`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180025861`
- `ADVAPI32!RegisterEventSourceW` at `0x1800258a3`
- `ADVAPI32!RegisterEventSourceW` at `0x18002634c`
- `ADVAPI32!RegisterEventSourceW` at `0x1800258a3`
- `ADVAPI32!RegisterEventSourceW` at `0x18002634c`
- `ADVAPI32!DeregisterEventSource` at `0x18002591a`
- `ADVAPI32!DeregisterEventSource` at `0x1800263ad`
- `ADVAPI32!DeregisterEventSource` at `0x18002591a`
- `ADVAPI32!DeregisterEventSource` at `0x1800263ad`
- `ADVAPI32!ReportEventW` at `0x180025907`
- `ADVAPI32!ReportEventW` at `0x18002639a`
- `ADVAPI32!ReportEventW` at `0x180025907`
- `ADVAPI32!ReportEventW` at `0x18002639a`

## string_xrefs

- `0x18002589a`: `SecurityCenter`
- `0x180026338`: `SecurityCenter`
- `0x18002630e`: `SECURITY_PRODUCT_STATE_OFF`
- `0x180025727`: `s_wscUpdateProductStatus`
- `0x180025816`: `s_wscUpdateProductStatus`
- `0x180025851`: `s_wscUpdateProductStatus`
- `0x180026317`: `SECURITY_PRODUCT_STATE_ON`
- `0x180026305`: `SECURITY_PRODUCT_STATE_SNOOZED`
- `0x1800262fc`: `SECURITY_PRODUCT_STATE_EXPIRED`

## pseudocode

```c
__int64 __fastcall s_wscUpdateProductStatus(void *a1, unsigned int a2, unsigned int a3, unsigned int a4)
{
  unsigned int v4; // r13d
  unsigned int v5; // ebx
  CThirdPartyManager *v7; // r10
  WORD v8; // r12
  unsigned int v9; // edi
  int v10; // ebx
  int v12; // esi
  CThirdPartyManager *v13; // r12
  unsigned int v14; // r14d
  struct CThirdPartyManager *v15; // r8
  __int64 v16; // rdx
  int IsCallerAMPPL; // r14d
  unsigned int v18; // eax
  CThirdPartyManager *v19; // rcx
  bool v20; // zf
  int CallerProcessPath; // ebx
  unsigned int v22; // eax
  CThirdPartyManager *v23; // rcx
  void *v24; // rbx
  int v25; // ebx
  unsigned int v26; // eax
  int v27; // edx
  int v28; // r8d
  CThirdPartyManager *v29; // rcx
  void *v30; // rbx
  ULONGLONG TickCount64; // rdi
  HANDLE v32; // rbx
  unsigned int v33; // r14d
  CRpcImpersonateClient *v34; // rcx
  int v35; // eax
  const wchar_t *v36; // r8
  const wchar_t *v37; // r9
  __int64 v38; // rdx
  __int64 v39; // rdx
  struct CExternalBase *v40; // rax
  int v41; // ebx
  unsigned int v42; // eax
  unsigned __int16 *v43; // rbx
  int updated; // r15d
  int IsAlerted; // eax
  CThirdPartyManager *v46; // r13
  unsigned int v47; // r14d
  int v48; // r12d
  unsigned int i; // esi
  CThirdPartyManager *v50; // rcx
  unsigned int v51; // ebx
  __int64 v52; // r9
  unsigned int v53; // ebx
  struct CExternalBase *v54; // rax
  CThirdPartyManager *v55; // rcx
  struct CWmiEventManagerAvFw *v56; // rsi
  int v57; // r14d
  __int64 v58; // rcx
  __int64 v59; // rsi
  const wchar_t *v60; // rax
  int IsDefender; // esi
  unsigned int v62; // eax
  CThirdPartyManager *v63; // rcx
  __int64 v64; // rcx
  int v65; // eax
  const wchar_t *v66; // rdx
  unsigned int v67; // r15d
  const wchar_t *v68; // rax
  DWORD v69; // esi
  HANDLE v70; // rbx
  unsigned __int16 **lpRawData; // r10
  struct CExternalBase *v72; // rcx
  int wNumStrings; // [rsp+28h] [rbp-71h]
  bool v74; // [rsp+50h] [rbp-49h] BYREF
  struct CExternalBase *v75; // [rsp+58h] [rbp-41h] BYREF
  int v76; // [rsp+60h] [rbp-39h]
  unsigned int v77; // [rsp+64h] [rbp-35h]
  unsigned __int16 *v78; // [rsp+68h] [rbp-31h] BYREF
  void *Block; // [rsp+70h] [rbp-29h] BYREF
  unsigned int v80; // [rsp+78h] [rbp-21h]
  unsigned int v81; // [rsp+7Ch] [rbp-1Dh]
  RPC_BINDING_HANDLE BindingHandle[2]; // [rsp+80h] [rbp-19h] BYREF
  unsigned __int16 v83[12]; // [rsp+90h] [rbp-9h] BYREF

  v4 = a2;
  v80 = a2;
  v81 = a4;
  v5 = a3;
  v75 = 0;
  v77 = a3;
  BindingHandle[0] = a1;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  v8 = 4;
  if ( !v4 )
  {
    v76 = 1;
    v74 = 0;
    IsCallerAMPPL = CSecurityVerificationManager::IsCallerAMPPL(a1, &v74);
    if ( IsCallerAMPPL < 0 )
    {
      Block = 0;
      v18 = RpcImpersonateClient(a1);
      if ( v18 )
      {
        v19 = WPP_GLOBAL_Control;
        v20 = WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control;
        goto LABEL_87;
      }
      CallerProcessPath = CSecurityVerificationManager::GetCallerProcessPath(a1, (unsigned __int16 **)&Block);
      v22 = RpcRevertToSelf();
      if ( v22 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_21:
          if ( CallerProcessPath >= 0 )
          {
            v24 = Block;
            if ( v23 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 )
              WPP_SF_SSd(
                *((_QWORD *)v23 + 2),
                195,
                (unsigned int)WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
                (unsigned int)L"s_wscUpdateProductStatus",
                (__int64)Block,
                IsCallerAMPPL);
            if ( v24 )
              operator delete(v24);
          }
          else if ( v23 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)v23 + 2),
              194,
              WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
              (unsigned int)CallerProcessPath);
            v9 = 0xFFFF;
            goto LABEL_69;
          }
          v9 = 0xFFFF;
          goto LABEL_69;
        }
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v22);
      }
      v23 = WPP_GLOBAL_Control;
      goto LABEL_21;
    }
    v12 = 0;
    if ( v74 )
    {
LABEL_62:
      LOBYTE(v16) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl'::`2'::impl,
        v16);
      AMPPLWmiDataUtils::LogAMPPLDataToWMI(
        (AMPPLWmiDataUtils *)a1,
        0,
        0,
        (const unsigned __int16 *)(unsigned int)IsCallerAMPPL,
        v12,
        wNumStrings);
      if ( g_bEnforceAmppl )
      {
        v9 = v12;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 196, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
        }
        v9 = 0;
      }
      if ( !v9 )
      {
        v13 = WscServiceUtils::g_pAntiVirusManager;
        v14 = 1;
        v15 = WscServiceUtils::g_pAntiVirusVerificationManager;
        goto LABEL_71;
      }
LABEL_69:
      WppLogUnregisterNonCompliantProduct(a1);
      s_wscUnregisterSecurityProduct(a1, SECURITY_PRODUCT_TYPE_ANTIVIRUS);
      v7 = WPP_GLOBAL_Control;
      v10 = 0;
      goto LABEL_77;
    }
    Block = 0;
    v18 = RpcImpersonateClient(a1);
    if ( v18 )
    {
      v19 = WPP_GLOBAL_Control;
      v20 = WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control;
      goto LABEL_87;
    }
    v12 = 1244;
    v25 = CSecurityVerificationManager::GetCallerProcessPath(a1, (unsigned __int16 **)&Block);
    v26 = RpcRevertToSelf();
    if ( v26 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_39:
        if ( v25 >= 0 )
        {
          v30 = Block;
          if ( v29 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 1) != 0 )
          {
            WPP_SF_SSl(*((_QWORD *)v29 + 2), v27, v28, (unsigned int)L"s_wscUpdateProductStatus", (__int64)Block);
            v29 = WPP_GLOBAL_Control;
          }
          if ( !v30 )
            goto LABEL_49;
          operator delete(v30);
        }
        else
        {
          if ( v29 == (CThirdPartyManager *)&WPP_GLOBAL_Control )
          {
LABEL_52:
            TickCount64 = GetTickCount64();
            if ( TickCount64 - qword_1800542D8 > 0xEA60 )
            {
              if ( g_bEnforceAmppl )
              {
                EvtLog_LogErrorWithHresult(0xC0000011, -2147023652);
              }
              else
              {
                v32 = RegisterEventSourceW(0, L"SecurityCenter");
                if ( v32 )
                {
                  if ( (int)StringCchPrintfW(v83, 9u, L"%08x", 2147943644LL) >= 0 )
                  {
                    Block = v83;
                    if ( !ReportEventW(v32, 4u, 0, 0xC0000011, 0, 1u, 0, (LPCWSTR *)&Block, 0) )
                      GetLastError();
                  }
                  DeregisterEventSource(v32);
                }
              }
              qword_1800542D8 = TickCount64;
            }
            v5 = v77;
            goto LABEL_62;
          }
          if ( (*((_BYTE *)v29 + 28) & 1) == 0 )
          {
LABEL_49:
            if ( v29 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 1) != 0 )
              WPP_SF_Sl(*((_QWORD *)v29 + 2), v27, v28, (unsigned int)L"s_wscUpdateProductStatus", 220);
            goto LABEL_52;
          }
          WPP_SF_d(*((_QWORD *)v29 + 2), 190, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, (unsigned int)v25);
        }
        v29 = WPP_GLOBAL_Control;
        goto LABEL_49;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v26);
    }
    v29 = WPP_GLOBAL_Control;
    goto LABEL_39;
  }
  if ( v4 != 1 )
  {
    if ( v4 != 2 )
    {
      v76 = 0;
      v9 = 87;
      v10 = 0;
      goto LABEL_77;
    }
    if ( v7 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v7 + 2), 233, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
    return 0;
  }
  v76 = 4;
  v12 = 0;
  v13 = WscServiceUtils::g_pFirewallManager;
  v14 = 2;
  v15 = WscServiceUtils::g_pFirewallVerificationManager;
LABEL_71:
  Block = v13;
  v9 = WscServiceUtils::CreateExternalBaseFromCaller(a1, v13, v15, &v75);
  if ( v9 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v9);
      v7 = WPP_GLOBAL_Control;
    }
    v10 = 0;
    goto LABEL_76;
  }
  v35 = CThirdPartyManager::PopulateProductRegistrationInformation(v13, v75);
  v36 = L"AS";
  if ( v35 < 0 )
  {
    v9 = 2;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        238,
        WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
        (unsigned int)v35);
      v7 = WPP_GLOBAL_Control;
      v10 = 0;
      goto LABEL_76;
    }
    goto LABEL_139;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    if ( v4 )
      v37 = L"FW";
    else
      v37 = L"AV";
    WPP_SF_SSDd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      235,
      (unsigned int)L"AS",
      (_DWORD)v37,
      *((_QWORD *)v75 + 2),
      v5,
      v81);
    v7 = WPP_GLOBAL_Control;
  }
  switch ( v5 )
  {
    case 0u:
      v39 = 4096;
      goto LABEL_114;
    case 1u:
      v39 = 0;
      goto LABEL_114;
    case 2u:
      v39 = 0x2000;
LABEL_114:
      CExternalBase::SetProductState(v75, v39, v36);
      goto LABEL_115;
  }
  if ( v5 != 3 )
  {
    v9 = 87;
    if ( v7 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
    {
      v38 = 237;
LABEL_105:
      WPP_SF_(*((_QWORD *)v7 + 2), v38, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
LABEL_115:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_116;
    }
    goto LABEL_116;
  }
  if ( v4 )
  {
    v9 = 87;
    if ( v7 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
    {
      v38 = 236;
      goto LABEL_105;
    }
LABEL_116:
    if ( v4 == 1 )
      goto LABEL_121;
    goto LABEL_117;
  }
  CExternalBase::SetProductState(v75, 0x4000, v36);
LABEL_117:
  v40 = v75;
  if ( v81 )
  {
    *((_DWORD *)v75 + 20) &= 0xFFFFFF0F;
  }
  else
  {
    *((_DWORD *)v75 + 20) &= 0xFFFFFF1F;
    *((_DWORD *)v40 + 20) |= 0x10u;
  }
  v7 = WPP_GLOBAL_Control;
LABEL_121:
  if ( !g_bEnforceAmppl || !g_bAmpplOneWayEnabled || !v12 )
    goto LABEL_139;
  v78 = 0;
  v18 = RpcImpersonateClient(a1);
  if ( v18 )
  {
    v19 = WPP_GLOBAL_Control;
    v20 = WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control;
LABEL_87:
    if ( !v20 && (*((_BYTE *)v19 + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v19 + 2), 27, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v18);
    RpcRaiseException(5);
  }
  v41 = CSecurityVerificationManager::GetCallerProcessPath(a1, &v78);
  v42 = RpcRevertToSelf();
  if ( v42 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_131;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v42);
  }
  v7 = WPP_GLOBAL_Control;
LABEL_131:
  if ( v41 >= 0 )
  {
    v43 = v78;
    if ( g_pOneWayAMPPLEnablementAgent )
    {
      WscServiceUtils::OneWayAMPPLEnablementAgent::AddNonCompliantProduct(g_pOneWayAMPPLEnablementAgent, v78);
      if ( !v43 )
        goto LABEL_138;
    }
    else
    {
      if ( v7 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)v7 + 2), 43, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids);
        v7 = WPP_GLOBAL_Control;
      }
      if ( !v43 )
        goto LABEL_139;
    }
    operator delete(v43);
    goto LABEL_138;
  }
  if ( v7 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v7 + 2), 42, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids, (unsigned int)v41);
LABEL_138:
    v7 = WPP_GLOBAL_Control;
  }
LABEL_139:
  v10 = 0;
  if ( v9 )
  {
LABEL_76:
    v8 = 4;
    goto LABEL_77;
  }
  updated = CThirdPartyManager::UpdateExternalProduct(v13, v75);
  IsAlerted = CThirdPartyManager::IsAlerted(v13);
  CAlertStatus::SetComponentAlerted(g_pAlertStatus, v14, IsAlerted);
  if ( updated < 0 )
  {
    v8 = 4;
    goto LABEL_206;
  }
  if ( v77 != 3 )
  {
    v7 = WPP_GLOBAL_Control;
LABEL_180:
    v56 = g_pWmiEventManagerAvFw;
    v57 = v76;
    if ( g_pWmiEventManagerAvFw )
    {
      v58 = *((_QWORD *)g_pWmiEventManagerAvFw + 8);
      if ( !v58 )
      {
        updated = -2147467259;
        v8 = 4;
LABEL_188:
        v9 = 1127;
        if ( v7 == (CThirdPartyManager *)&WPP_GLOBAL_Control )
          goto LABEL_203;
        if ( (*((_BYTE *)v7 + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v7 + 2), 241, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, (unsigned int)updated);
          v7 = WPP_GLOBAL_Control;
        }
        goto LABEL_195;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 8LL))(v58);
      v59 = *((_QWORD *)v56 + 8);
      v8 = 4;
      updated = CExternalBase::UpdatePersistentStore(v75, v59, v4, 4);
      if ( updated < 0
        && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          240,
          WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
          (unsigned int)updated);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      SqmHelper::SetThirdPartyStatus(
        WscServiceUtils::g_pAntiVirusManager,
        WscServiceUtils::g_pAntiSpywareManager,
        WscServiceUtils::g_pFirewallManager);
      v7 = WPP_GLOBAL_Control;
      if ( updated < 0 )
        goto LABEL_188;
    }
    else
    {
      v9 = 1127;
      if ( v7 == (CThirdPartyManager *)&WPP_GLOBAL_Control )
      {
        v8 = 4;
        goto LABEL_203;
      }
      if ( (*((_BYTE *)v7 + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)v7 + 2), 242, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
        v7 = WPP_GLOBAL_Control;
      }
      v8 = 4;
    }
LABEL_195:
    if ( v7 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
    {
      if ( v4 )
      {
        v60 = L"FW";
        if ( v4 != 1 )
          v60 = L"AS";
      }
      else
      {
        v60 = L"AV";
      }
      WPP_SF_S(*((_QWORD *)v7 + 2), 243, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v60);
    }
LABEL_203:
    g_dwProductStatusInitiated |= v57;
    CAlertStatus::FireNotificationEvents(g_pAlertStatus, 0);
    if ( updated >= 0 )
    {
      v7 = WPP_GLOBAL_Control;
      goto LABEL_77;
    }
LABEL_206:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_208;
  }
  v46 = WscServiceUtils::g_pAntiVirusManager;
  LODWORD(v78) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)WscServiceUtils::g_pAntiVirusManager + 16));
  v47 = *(_DWORD *)(*((_QWORD *)v46 + 7) + 48LL);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v46 + 16));
  v48 = 0;
  if ( v47 <= 0x20 )
  {
    if ( !v47 )
    {
LABEL_177:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_178;
    }
  }
  else
  {
    v47 = 32;
  }
  for ( i = 0; i < v47; ++i )
  {
    CThirdPartyManager::GetProductBitField(v46, i, (unsigned int *)&v78);
    v51 = (unsigned int)v78;
    if ( ((unsigned int)v78 & 0x40000) == 0 )
      goto LABEL_169;
    v52 = (unsigned __int16)v78 & 0xF00;
    if ( ((unsigned __int16)v78 & 0xF00) != 0 )
    {
      if ( (_DWORD)v52 == 256 )
        goto LABEL_161;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids, v52);
      }
    }
    if ( (unsigned int)ExtractProductState(v51) == 4096 )
      goto LABEL_177;
LABEL_161:
    if ( (unsigned int)ExtractProductState(v51) == 0x4000 )
      goto LABEL_168;
    v53 = v51 & 0xF00000;
    if ( (v53 & 0xFFCFFFFF) == 0 && v53 != 3145728 )
      goto LABEL_169;
    if ( v53 == 3145728 )
    {
LABEL_168:
      v48 = 1;
      goto LABEL_169;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids, v53);
LABEL_169:
      v7 = WPP_GLOBAL_Control;
      continue;
    }
  }
  if ( !v48 )
  {
LABEL_178:
    v4 = v80;
    v10 = 0;
    goto LABEL_180;
  }
  CThirdPartyManager::ClearAllNotifications(v50);
  v54 = v75;
  v55 = (CThirdPartyManager *)Block;
  *((_DWORD *)v75 + 20) &= 0xFF3FFFFF;
  *((_DWORD *)v54 + 20) |= 0x300000u;
  updated = CThirdPartyManager::UpdateExternalProduct(v55, v75);
  v7 = WPP_GLOBAL_Control;
  v10 = 1;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( updated >= 0 )
  {
    v4 = v80;
    goto LABEL_180;
  }
  v8 = 4;
LABEL_208:
  v9 = (unsigned __int16)updated;
  if ( v7 == (CThirdPartyManager *)&WPP_GLOBAL_Control )
  {
LABEL_80:
    if ( v7 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)v7 + 2), 10, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    if ( (*((_BYTE *)v7 + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v7 + 2), 244, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, (unsigned int)updated);
      v7 = WPP_GLOBAL_Control;
    }
LABEL_77:
    if ( v7 != (CThirdPartyManager *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v7 + 28) & 0x10) != 0 )
      {
        WPP_SF_(*((_QWORD *)v7 + 2), 10, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
        v7 = WPP_GLOBAL_Control;
      }
      goto LABEL_80;
    }
  }
  v33 = v80;
  if ( !v9 )
  {
    if ( (v80 & 0xFFFFFFFD) == 0 )
    {
      v18 = RpcImpersonateClient(BindingHandle[0]);
      if ( v18 )
      {
        v19 = WPP_GLOBAL_Control;
        v20 = WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control;
        goto LABEL_87;
      }
      IsDefender = CRpcImpersonateClient::IsDefender(v34);
      v62 = RpcRevertToSelf();
      if ( v62 )
      {
        v63 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v62);
        }
      }
      LODWORD(v78) = 1;
      CThirdPartyManager::OutOfBoxProductProtected(v63, (int *)&v78, 0, 0);
      if ( !IsDefender )
      {
        if ( v77 )
        {
          if ( (_DWORD)v78 )
            goto LABEL_228;
LABEL_226:
          v64 = 1;
LABEL_227:
          SetDefenderStatus((DefenderStateUtils *)v64, 2u);
          goto LABEL_228;
        }
LABEL_222:
        v64 = 0;
        goto LABEL_227;
      }
      if ( (v77 & 0xFFFFFFFD) == 0 )
      {
        if ( (_DWORD)v78 )
          goto LABEL_222;
        if ( !v77 )
          goto LABEL_228;
      }
      if ( v77 != 2 && !(_DWORD)v78 )
        goto LABEL_226;
LABEL_228:
      v7 = WPP_GLOBAL_Control;
    }
    if ( v10 )
    {
      if ( v7 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)v7 + 2), 245, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
      v65 = WscMonitorExpiredState();
      if ( v65 < 0 )
      {
        v9 = (unsigned __int16)v65;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            246,
            WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
            (unsigned int)v65);
        }
      }
    }
  }
  if ( v75 )
    v66 = (const wchar_t *)*((_QWORD *)v75 + 2);
  else
    v66 = L"(unknown)";
  v67 = v77;
  if ( v77 )
  {
    switch ( v77 )
    {
      case 1u:
        v68 = L"SECURITY_PRODUCT_STATE_OFF";
        break;
      case 2u:
        v68 = L"SECURITY_PRODUCT_STATE_SNOOZED";
        break;
      case 3u:
        v68 = L"SECURITY_PRODUCT_STATE_EXPIRED";
        break;
      default:
        v68 = L"INVALID STATE";
        break;
    }
  }
  else
  {
    v68 = L"SECURITY_PRODUCT_STATE_ON";
  }
  BindingHandle[0] = (RPC_BINDING_HANDLE)v66;
  BindingHandle[1] = (RPC_BINDING_HANDLE)v68;
  v69 = 15;
  LODWORD(v78) = v9;
  if ( v9 )
  {
    v69 = -1073741808;
    v8 = 1;
  }
  v70 = RegisterEventSourceW(0, L"SecurityCenter");
  if ( v70 )
  {
    lpRawData = &v78;
    if ( !v9 )
      lpRawData = 0;
    if ( !ReportEventW(v70, v8, 0, v69, 0, 2u, v9 != 0 ? 4 : 0, (LPCWSTR *)BindingHandle, lpRawData) )
      GetLastError();
    DeregisterEventSource(v70);
  }
  v72 = v75;
  if ( v75 )
  {
    if ( (v9 & 0x80000000) == 0 )
    {
      WscTelemetryEventWriteProductUpdate(v33, v67, v81, v75);
      v72 = v75;
    }
    if ( v72 )
      (**(void (__fastcall ***)(struct CExternalBase *, __int64))v72)(v72, 1);
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 247, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180025520  push    rbp
0x180025522  push    rbx
0x180025523  push    rdi
0x180025524  push    r12
0x180025526  push    r13
0x180025528  push    r14
0x18002552a  push    r15
0x18002552c  lea     rbp, [rsp-27h]
0x180025531  sub     rsp, 0C0h
0x180025538  mov     rax, cs:__security_cookie
0x18002553f  xor     rax, rsp
0x180025542  mov     [rbp+57h+var_48], rax
0x180025546  mov     r13d, edx
0x180025549  mov     [rbp+57h+var_78], edx
0x18002554c  xor     edx, edx
0x18002554e  mov     [rbp+57h+var_74], r9d
0x180025552  mov     ebx, r8d
0x180025555  mov     [rbp+57h+var_98], rdx
0x180025559  mov     [rbp+57h+var_8C], ebx
0x18002555c  mov     r15, rcx
0x18002555f  mov     [rbp+57h+BindingHandle], rcx
0x180025563  mov     r10, cs:WPP_GLOBAL_Control
0x18002556a  lea     rdi, WPP_GLOBAL_Control
0x180025571  cmp     r10, rdi
0x180025574  jz      short loc_18002559B
0x180025576  test    byte ptr [r10+1Ch], 8
0x18002557b  jz      short loc_18002559B
0x18002557d  mov     rcx, [r10+10h]
0x180025581  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180025588  mov     edx, 0E8h
0x18002558d  call    WPP_SF_
0x180025592  mov     r10, cs:WPP_GLOBAL_Control
0x180025599  xor     edx, edx
0x18002559b  mov     [rsp+0F0h+var_38], rsi
0x1800255a3  mov     ecx, r13d
0x1800255a6  mov     r12d, 4
0x1800255ac  mov     r14d, 1
0x1800255b2  test    r13d, r13d
0x1800255b5  jz      loc_180025657
0x1800255bb  sub     ecx, r14d
0x1800255be  jz      short loc_180025638
0x1800255c0  cmp     ecx, r14d
0x1800255c3  jz      short loc_180025611
0x1800255c5  cmp     r13d, 2
0x1800255c9  jz      short loc_180025611
0x1800255cb  mov     [rbp+57h+var_90], edx
0x1800255ce  test    r13d, r13d
0x1800255d1  jz      loc_18002565B
0x1800255d7  mov     ecx, r13d
0x1800255da  mov     [rbp+57h+var_90], edx
0x1800255dd  mov     esi, edx
0x1800255df  sub     ecx, r14d
0x1800255e2  jz      short loc_18002563E
0x1800255e4  cmp     ecx, r14d
0x1800255e7  jz      short loc_1800255F5
0x1800255e9  mov     edi, 57h ; 'W'
0x1800255ee  mov     ebx, edx
0x1800255f0  jmp     loc_180025A1C
0x1800255f5  mov     r12, cs:?g_pAntiSpywareManager@WscServiceUtils@@3PEAVCAntiSpywareManager@@EA; CAntiSpywareManager * WscServiceUtils::g_pAntiSpywareManager
0x1800255fc  mov     r14d, 8
0x180025602  mov     r8, cs:?g_pAntiSpywareVerificationManager@WscServiceUtils@@3PEAVCSecurityVerificationManagerAs@@EA; CSecurityVerificationManagerAs * WscServiceUtils::g_pAntiSpywareVerificationManager
0x180025609  mov     [rbp+57h+var_90], edx
0x18002560c  jmp     loc_1800259BE
0x180025611  cmp     r10, rdi
0x180025614  jz      short loc_180025631
0x180025616  test    [r10+1Ch], r14b
0x18002561a  jz      short loc_180025631
0x18002561c  mov     rcx, [r10+10h]
0x180025620  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180025627  mov     edx, 0E9h
0x18002562c  call    WPP_SF_
0x180025631  xor     eax, eax
0x180025633  jmp     loc_18002641C
0x180025638  mov     [rbp+57h+var_90], r12d
0x18002563c  mov     esi, edx
0x18002563e  mov     r12, cs:?g_pFirewallManager@WscServiceUtils@@3PEAVCFirewallManager@@EA; CFirewallManager * WscServiceUtils::g_pFirewallManager
0x180025645  mov     r14d, 2
0x18002564b  mov     r8, cs:?g_pFirewallVerificationManager@WscServiceUtils@@3PEAVCSecurityVerificationManagerFw@@EA; CSecurityVerificationManagerFw * WscServiceUtils::g_pFirewallVerificationManager
0x180025652  jmp     loc_1800259BE
0x180025657  mov     [rbp+57h+var_90], r14d
0x18002565b  lea     rdx, [rbp+57h+var_A0]; bool *
0x18002565f  mov     [rbp+57h+var_A0], 0
0x180025663  mov     rcx, r15; ClientBinding
0x180025666  call    ?IsCallerAMPPL@CSecurityVerificationManager@@SAJPEAXPEA_N@Z; CSecurityVerificationManager::IsCallerAMPPL(void *,bool *)
0x18002566b  mov     r14d, eax
0x18002566e  test    eax, eax
0x180025670  jns     loc_180025760
0x180025676  mov     rcx, r15; BindingHandle
0x180025679  mov     [rbp+57h+Block], 0
0x180025681  call    cs:__imp_RpcImpersonateClient
0x180025687  test    eax, eax
0x180025689  jz      short loc_18002569A
0x18002568b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025692  cmp     rcx, rdi
0x180025695  jmp     loc_180025AA8
0x18002569a  lea     rdx, [rbp+57h+Block]; unsigned __int16 **
0x18002569e  mov     rcx, r15; void *
0x1800256a1  call    ?GetCallerProcessPath@CSecurityVerificationManager@@SAJPEAXPEAPEAG@Z; CSecurityVerificationManager::GetCallerProcessPath(void *,ushort * *)
0x1800256a6  mov     ebx, eax
0x1800256a8  call    cs:__imp_RpcRevertToSelf
0x1800256ae  test    eax, eax
0x1800256b0  jz      short loc_1800256DC
0x1800256b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256b9  cmp     rcx, rdi
0x1800256bc  jz      short loc_1800256E3
0x1800256be  test    byte ptr [rcx+1Ch], 1
0x1800256c2  jz      short loc_1800256E3
0x1800256c4  mov     rcx, [rcx+10h]
0x1800256c8  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x1800256cf  mov     edx, 1Ch
0x1800256d4  mov     r9d, eax
0x1800256d7  call    WPP_SF_d
0x1800256dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256e3  test    ebx, ebx
0x1800256e5  jns     short loc_180025714
0x1800256e7  cmp     rcx, rdi
0x1800256ea  jz      short loc_180025756
0x1800256ec  test    byte ptr [rcx+1Ch], 1
0x1800256f0  jz      short loc_180025756
0x1800256f2  mov     rcx, [rcx+10h]
0x1800256f6  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x1800256fd  mov     edx, 0C2h
0x180025702  mov     r9d, ebx
0x180025705  call    WPP_SF_d
0x18002570a  mov     edi, 0FFFFh
0x18002570f  jmp     loc_18002598D
0x180025714  mov     rbx, [rbp+57h+Block]
0x180025718  cmp     rcx, rdi
0x18002571b  jz      short loc_180025749
0x18002571d  test    byte ptr [rcx+1Ch], 1
0x180025721  jz      short loc_180025749
0x180025723  mov     rcx, [rcx+10h]
0x180025727  lea     r9, aSWscupdateprod_0; "s_wscUpdateProductStatus"
0x18002572e  mov     edx, 0C3h
0x180025733  mov     dword ptr [rsp+0F0h+wNumStrings], r14d
0x180025738  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x18002573f  mov     [rsp+0F0h+lpUserSid], rbx
0x180025744  call    WPP_SF_SSd
0x180025749  test    rbx, rbx
0x18002574c  jz      short loc_180025756
0x18002574e  mov     rcx, rbx; Block
0x180025751  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025756  mov     edi, 0FFFFh
0x18002575b  jmp     loc_18002598D
0x180025760  xor     esi, esi
0x180025762  cmp     [rbp+57h+var_A0], sil
0x180025766  jnz     loc_180025931
0x18002576c  mov     rcx, r15; BindingHandle
0x18002576f  mov     [rbp+57h+Block], rsi
0x180025773  call    cs:__imp_RpcImpersonateClient
0x180025779  test    eax, eax
0x18002577b  jz      short loc_18002578C
0x18002577d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025784  cmp     rcx, rdi
0x180025787  jmp     loc_180025AA8
0x18002578c  lea     rdx, [rbp+57h+Block]; unsigned __int16 **
0x180025790  mov     rcx, r15; void *
0x180025793  mov     esi, 4DCh
0x180025798  call    ?GetCallerProcessPath@CSecurityVerificationManager@@SAJPEAXPEAPEAG@Z; CSecurityVerificationManager::GetCallerProcessPath(void *,ushort * *)
0x18002579d  mov     ebx, eax
0x18002579f  call    cs:__imp_RpcRevertToSelf
0x1800257a5  test    eax, eax
0x1800257a7  jz      short loc_1800257D3
0x1800257a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257b0  cmp     rcx, rdi
0x1800257b3  jz      short loc_1800257DA
0x1800257b5  test    byte ptr [rcx+1Ch], 1
0x1800257b9  jz      short loc_1800257DA
0x1800257bb  mov     rcx, [rcx+10h]
0x1800257bf  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x1800257c6  mov     edx, 1Ch
0x1800257cb  mov     r9d, eax
0x1800257ce  call    WPP_SF_d
0x1800257d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257da  test    ebx, ebx
0x1800257dc  jns     short loc_180025803
0x1800257de  cmp     rcx, rdi
0x1800257e1  jz      short loc_180025861
0x1800257e3  test    byte ptr [rcx+1Ch], 1
0x1800257e7  jz      short loc_180025842
0x1800257e9  mov     rcx, [rcx+10h]
0x1800257ed  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x1800257f4  mov     edx, 0BEh
0x1800257f9  mov     r9d, ebx
0x1800257fc  call    WPP_SF_d
0x180025801  jmp     short loc_18002583B
0x180025803  mov     rbx, [rbp+57h+Block]
0x180025807  cmp     rcx, rdi
0x18002580a  jz      short loc_18002582E
0x18002580c  test    byte ptr [rcx+1Ch], 1
0x180025810  jz      short loc_18002582E
0x180025812  mov     rcx, [rcx+10h]
0x180025816  lea     r9, aSWscupdateprod_0; "s_wscUpdateProductStatus"
0x18002581d  mov     [rsp+0F0h+lpUserSid], rbx
0x180025822  call    WPP_SF_SSl
0x180025827  mov     rcx, cs:WPP_GLOBAL_Control
0x18002582e  test    rbx, rbx
0x180025831  jz      short loc_180025842
0x180025833  mov     rcx, rbx; Block
0x180025836  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002583b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025842  cmp     rcx, rdi
0x180025845  jz      short loc_180025861
0x180025847  test    byte ptr [rcx+1Ch], 1
0x18002584b  jz      short loc_180025861
0x18002584d  mov     rcx, [rcx+10h]
0x180025851  lea     r9, aSWscupdateprod_0; "s_wscUpdateProductStatus"
0x180025858  mov     dword ptr [rsp+0F0h+lpUserSid], esi
0x18002585c  call    WPP_SF_Sl
0x180025861  call    cs:__imp_GetTickCount64
0x180025867  mov     rdi, rax
0x18002586a  sub     rax, cs:qword_1800542D8
0x180025871  cmp     rax, 0EA60h
0x180025877  jbe     loc_180025927
0x18002587d  cmp     cs:?g_bEnforceAmppl@@3_NA, 0; bool g_bEnforceAmppl
0x180025884  jz      short loc_18002589A
0x180025886  mov     edx, 800704DCh; int
0x18002588b  mov     ecx, 0C0000011h; dwEventID
0x180025890  call    ?EvtLog_LogErrorWithHresult@@YAXKJ@Z; EvtLog_LogErrorWithHresult(ulong,long)
0x180025895  jmp     loc_180025920
0x18002589a  lea     rdx, SourceName; "SecurityCenter"
0x1800258a1  xor     ecx, ecx; lpUNCServerName
0x1800258a3  call    cs:__imp_RegisterEventSourceW
0x1800258a9  mov     rbx, rax
0x1800258ac  test    rax, rax
0x1800258af  jz      short loc_180025920
0x1800258b1  mov     r9d, 800704DCh
0x1800258b7  lea     r8, a08x; "%08x"
0x1800258be  mov     edx, 9; unsigned __int64
0x1800258c3  lea     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x1800258c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800258cc  test    eax, eax
0x1800258ce  js      short loc_180025917
0x1800258d0  xor     ecx, ecx
0x1800258d2  lea     rax, [rbp+57h+var_60]
0x1800258d6  mov     [rsp+0F0h+lpRawData], rcx; lpRawData
0x1800258db  xor     r8d, r8d; wCategory
0x1800258de  mov     [rbp+57h+Block], rax
0x1800258e2  mov     edx, r12d; wType
0x1800258e5  lea     rax, [rbp+57h+Block]
0x1800258e9  mov     r9d, 0C0000011h; dwEventID
0x1800258ef  mov     [rsp+0F0h+lpStrings], rax; lpStrings
0x1800258f4  mov     [rsp+0F0h+dwDataSize], ecx; dwDataSize
0x1800258f8  mov     [rsp+0F0h+wNumStrings], 1; int
0x1800258ff  mov     [rsp+0F0h+lpUserSid], rcx; lpUserSid
0x180025904  mov     rcx, rbx; hEventLog
0x180025907  call    cs:__imp_ReportEventW
0x18002590d  test    eax, eax
0x18002590f  jnz     short loc_180025917
0x180025911  call    cs:__imp_GetLastError
0x180025917  mov     rcx, rbx; hEventLog
0x18002591a  call    cs:__imp_DeregisterEventSource
0x180025920  mov     cs:qword_1800542D8, rdi
0x180025927  mov     ebx, [rbp+57h+var_8C]
0x18002592a  lea     rdi, WPP_GLOBAL_Control
0x180025931  mov     dl, 1
0x180025933  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl(void)'::`2'::impl
0x18002593a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002593f  mov     r9d, r14d; unsigned __int16 *
0x180025942  mov     dword ptr [rsp+0F0h+lpUserSid], esi; struct CExternalBase **
0x180025946  xor     r8d, r8d; unsigned __int16 *
0x180025949  xor     edx, edx; void *
0x18002594b  mov     rcx, r15; this
0x18002594e  call    ?LogAMPPLDataToWMI@AMPPLWmiDataUtils@@YAJPEAXPEBG1JJ@Z; AMPPLWmiDataUtils::LogAMPPLDataToWMI(void *,ushort const *,ushort const *,long,long)
0x180025953  cmp     cs:?g_bEnforceAmppl@@3_NA, 0; bool g_bEnforceAmppl
0x18002595a  jnz     short loc_180025987
0x18002595c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025963  cmp     rcx, rdi
0x180025966  jz      short loc_180025983
0x180025968  test    byte ptr [rcx+1Ch], 10h
0x18002596c  jz      short loc_180025983
0x18002596e  mov     rcx, [rcx+10h]
0x180025972  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180025979  mov     edx, 0C4h
0x18002597e  call    WPP_SF_
0x180025983  xor     edi, edi
0x180025985  jmp     short loc_180025989
0x180025987  mov     edi, esi
0x180025989  test    edi, edi
0x18002598b  jz      short loc_1800259AA
0x18002598d  mov     rcx, r15; void *
0x180025990  call    ?WppLogUnregisterNonCompliantProduct@@YAJPEAX@Z; WppLogUnregisterNonCompliantProduct(void *)
0x180025995  xor     edx, edx; enum _SECURITY_PRODUCT_TYPE
0x180025997  mov     rcx, r15; void *
0x18002599a  call    s_wscUnregisterSecurityProduct
0x18002599f  mov     r10, cs:WPP_GLOBAL_Control
0x1800259a6  xor     ebx, ebx
0x1800259a8  jmp     short loc_180025A1C
0x1800259aa  mov     r12, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; CAntiVirusManager * WscServiceUtils::g_pAntiVirusManager
0x1800259b1  mov     r14d, 1
0x1800259b7  mov     r8, cs:?g_pAntiVirusVerificationManager@WscServiceUtils@@3PEAVCSecurityVerificationManagerAv@@EA; struct CThirdPartyManager *
0x1800259be  lea     r9, [rbp+57h+var_98]; struct CSecurityVerificationManager *
0x1800259c2  mov     [rbp+57h+Block], r12
0x1800259c6  mov     rdx, r12; void *
0x1800259c9  mov     rcx, r15; ClientBinding
0x1800259cc  call    ?CreateExternalBaseFromCaller@WscServiceUtils@@YAJPEAXPEAVCThirdPartyManager@@PEAVCSecurityVerificationManager@@PEAPEAVCExternalBase@@@Z; WscServiceUtils::CreateExternalBaseFromCaller(void *,CThirdPartyManager *,CSecurityVerificationManager *,CExternalBase * *)
0x1800259d1  mov     edi, eax
0x1800259d3  test    eax, eax
0x1800259d5  jz      loc_180025AD4
0x1800259db  mov     r10, cs:WPP_GLOBAL_Control
  ... truncated ...
```
