# s_wscUnregisterSecurityProduct

- ea: `0x1800250c0`
- end: `0x18002550d`
- name: `s_wscUnregisterSecurityProduct`
- size: `1101`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `5`
- callee_count: `23`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180024630`
- `0x180024b40`
- `0x180025520`
- `0x180026450`
- `0x1800337d0`

## callees

- `0x180002e30`
- `0x180005220`
- `0x180008e48`
- `0x180019850`
- `0x18001c218`
- `0x18001c4c0`
- `0x18001c6dc`
- `0x18001fdd8`
- `0x180020018`
- `0x1800202e8`
- `0x180022cb0`
- `0x18002400c`
- `0x1800250c0`
- `0x1800281c4`
- `0x180029158`
- `0x180031cd0`
- `0x180032054`
- `0x180032e48`
- `0x180032fc4`
- `0x1800356b4`
- `0x180037a0c`
- `0x18003d294`
- `0x180042010`

## string_xrefs

- `0x180025131`: `s_wscUnregisterSecurityProduct`

## pseudocode

```c
__int64 __fastcall s_wscUnregisterSecurityProduct(void *a1, void *a2)
{
  unsigned int v2; // r15d
  enum _SECURITY_PRODUCT_TYPE v3; // esi
  unsigned int v6; // ebx
  unsigned int v7; // r13d
  CThirdPartyManager *v8; // rax
  struct CThirdPartyManager *v9; // r8
  unsigned int v10; // eax
  struct CExternalBase *v11; // rdx
  const wchar_t *v12; // r8
  const wchar_t *v13; // r9
  CThirdPartyManager *v14; // r15
  int IsAlerted; // eax
  int v16; // edx
  int WbemServices; // r15d
  struct IWbemServices *v18; // r13
  int v19; // eax
  CThirdPartyManager *v20; // rcx
  const wchar_t *v21; // rax
  struct CWmiEventManagerAvFw *v22; // rcx
  struct CExternalBase *v23; // rcx
  struct IWbemServices *v24; // [rsp+30h] [rbp-10h] BYREF
  int v25; // [rsp+88h] [rbp+48h] BYREF
  CThirdPartyManager *v26; // [rsp+90h] [rbp+50h] BYREF
  struct CExternalBase *v27; // [rsp+98h] [rbp+58h] BYREF

  v2 = 0;
  v3 = (int)a2;
  v27 = 0;
  v25 = 0;
  LODWORD(v26) = 0;
  if ( (_DWORD)a2 == 2 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 211, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
    }
    return 0;
  }
  if ( !(_DWORD)a2 )
  {
    ValidateCallerAMPPL((int *)&v26, &v25, a1, L"s_wscUnregisterSecurityProduct", 0, 0);
    if ( v25 )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2));
      }
    }
  }
  if ( g_bEnforceAmppl && g_bAmpplOneWayEnabled && (_DWORD)v26 )
    WscServiceUtils::RemoveNonCompliantProduct((WscServiceUtils *)a1, a2);
  if ( v3 )
  {
    if ( v3 == SECURITY_PRODUCT_TYPE_FIREWALL )
    {
      v8 = WscServiceUtils::g_pFirewallManager;
      v7 = 2;
      v9 = WscServiceUtils::g_pFirewallVerificationManager;
    }
    else
    {
      if ( v3 != SECURITY_PRODUCT_TYPE_ANTISPYWARE )
      {
        v6 = 87;
        v26 = 0;
        v7 = 0;
        goto LABEL_26;
      }
      v8 = WscServiceUtils::g_pAntiSpywareManager;
      v7 = 8;
      v9 = WscServiceUtils::g_pAntiSpywareVerificationManager;
    }
  }
  else
  {
    v8 = WscServiceUtils::g_pAntiVirusManager;
    v7 = 1;
    v9 = WscServiceUtils::g_pAntiVirusVerificationManager;
  }
  v26 = v8;
  v10 = WscServiceUtils::CreateExternalBaseFromCaller(a1, v8, v9, &v27);
  v6 = v10;
  if ( !v10 )
    goto LABEL_27;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 213, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v10);
LABEL_26:
  v2 = v6;
LABEL_27:
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl'::`2'::impl,
    a2);
  AMPPLWmiDataUtils::CleanupAMPPLDataFromWMI(v27, v11);
  if ( !v2 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v12 = L"Unknown";
      if ( *((_QWORD *)v27 + 2) )
        v12 = (const wchar_t *)*((_QWORD *)v27 + 2);
      if ( v3 )
      {
        v13 = L"FW";
        if ( v3 != SECURITY_PRODUCT_TYPE_FIREWALL )
          v13 = L"AS";
      }
      else
      {
        v13 = L"AV";
      }
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        214,
        (unsigned int)WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
        (_DWORD)v13,
        (__int64)v12);
    }
    v14 = v26;
    v24 = 0;
    v25 = CThirdPartyManager::RemoveExternalProduct(v26, v27);
    IsAlerted = CThirdPartyManager::IsAlerted(v14);
    CAlertStatus::SetComponentAlerted(g_pAlertStatus, v7, IsAlerted);
    if ( v25 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          219,
          WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
          (unsigned int)v25);
      }
      v6 = 2;
      goto LABEL_63;
    }
    if ( g_pWmiEventManagerAvFw )
    {
      WbemServices = CWmiEventManager::GetWbemServices(g_pWmiEventManagerAvFw, v16, &v24);
      if ( WbemServices >= 0 )
      {
        v18 = v24;
        v19 = CExternalBase::RemoveFromPersistentStore(v27, v24, v3);
        WbemServices = v19;
        if ( v19 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            215,
            WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
            (unsigned int)v19);
        }
        ((void (__fastcall *)(struct IWbemServices *))v18->lpVtbl->Release)(v18);
        SqmHelper::SetThirdPartyStatus(
          WscServiceUtils::g_pAntiVirusManager,
          WscServiceUtils::g_pAntiSpywareManager,
          WscServiceUtils::g_pFirewallManager);
        if ( WbemServices >= 0 )
        {
          v20 = WPP_GLOBAL_Control;
          goto LABEL_54;
        }
      }
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_53:
        v6 = 1127;
LABEL_54:
        if ( v20 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 4) != 0 )
        {
          if ( v3 )
          {
            v21 = L"FW";
            if ( v3 != SECURITY_PRODUCT_TYPE_FIREWALL )
              v21 = L"AS";
          }
          else
          {
            v21 = L"AV";
          }
          WPP_SF_S(*((_QWORD *)v20 + 2), 218, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v21);
        }
        CAlertStatus::FireNotificationEvents(g_pAlertStatus, 0);
        goto LABEL_62;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        216,
        WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
        (unsigned int)WbemServices);
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_53;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 217, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
    }
    v20 = WPP_GLOBAL_Control;
    goto LABEL_53;
  }
LABEL_62:
  v14 = v26;
LABEL_63:
  if ( !(unsigned int)WscDSA_FeatureIsEnabled() || v6 || v3 )
  {
    if ( !(unsigned int)WscDSA_FeatureIsEnabled() && !v6 && v3 == SECURITY_PRODUCT_TYPE_ANTIVIRUS )
      SetDefenderStatus((DefenderStateUtils *)1, 3u);
  }
  else
  {
    WscDSA_UnregisterCallback(v22, v14, v27);
  }
  v23 = v27;
  if ( v27 )
  {
    if ( !v6 )
    {
      WscTelemetryEventWriteProductDeregistration(v3, v27);
      v23 = v27;
    }
    if ( v23 )
      (**(void (__fastcall ***)(struct CExternalBase *, __int64))v23)(v23, 1);
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 220, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1800250c0  push    rbp
0x1800250c2  push    rbx
0x1800250c3  push    rsi
0x1800250c4  push    r12
0x1800250c6  push    r13
0x1800250c8  push    r14
0x1800250ca  push    r15
0x1800250cc  mov     rbp, rsp
0x1800250cf  sub     rsp, 40h
0x1800250d3  xor     r15d, r15d
0x1800250d6  mov     esi, edx
0x1800250d8  mov     [rbp+arg_18], r15
0x1800250dc  mov     rbx, rcx
0x1800250df  mov     [rbp+arg_8], r15d
0x1800250e3  mov     dword ptr [rbp+arg_10], r15d
0x1800250e7  cmp     edx, 2
0x1800250ea  jnz     short loc_180025121
0x1800250ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800250f3  lea     r14, WPP_GLOBAL_Control
0x1800250fa  cmp     rcx, r14
0x1800250fd  jz      short loc_18002511A
0x1800250ff  test    byte ptr [rcx+1Ch], 1
0x180025103  jz      short loc_18002511A
0x180025105  mov     rcx, [rcx+10h]
0x180025109  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180025110  mov     edx, 0D3h
0x180025115  call    WPP_SF_
0x18002511a  xor     eax, eax
0x18002511c  jmp     loc_1800254FD
0x180025121  lea     r14, WPP_GLOBAL_Control
0x180025128  test    esi, esi
0x18002512a  jnz     short loc_180025171
0x18002512c  mov     [rsp+40h+var_18], r15; unsigned __int16 *
0x180025131  lea     r9, aSWscunregister; "s_wscUnregisterSecurityProduct"
0x180025138  mov     r8, rbx; void *
0x18002513b  mov     [rsp+40h+var_20], r15; struct CExternalBase **
0x180025140  lea     rdx, [rbp+arg_8]; int *
0x180025144  lea     rcx, [rbp+arg_10]; int *
0x180025148  call    ?ValidateCallerAMPPL@@YAJPEAJ0PEAXPEBG22@Z; ValidateCallerAMPPL(long *,long *,void *,ushort const *,ushort const *,ushort const *)
0x18002514d  mov     r9d, [rbp+arg_8]
0x180025151  test    r9d, r9d
0x180025154  jz      short loc_180025171
0x180025156  mov     rcx, cs:WPP_GLOBAL_Control
0x18002515d  cmp     rcx, r14
0x180025160  jz      short loc_180025171
0x180025162  test    byte ptr [rcx+1Ch], 10h
0x180025166  jz      short loc_180025171
0x180025168  mov     rcx, [rcx+10h]
0x18002516c  call    WPP_SF_l
0x180025171  cmp     cs:?g_bEnforceAmppl@@3_NA, r15b; bool g_bEnforceAmppl
0x180025178  jz      short loc_180025191
0x18002517a  cmp     cs:?g_bAmpplOneWayEnabled@@3_NA, r15b; bool g_bAmpplOneWayEnabled
0x180025181  jz      short loc_180025191
0x180025183  cmp     dword ptr [rbp+arg_10], r15d
0x180025187  jz      short loc_180025191
0x180025189  mov     rcx, rbx; this
0x18002518c  call    ?RemoveNonCompliantProduct@WscServiceUtils@@YAJPEAX@Z; WscServiceUtils::RemoveNonCompliantProduct(void *)
0x180025191  lea     r12, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180025198  mov     ecx, esi
0x18002519a  test    esi, esi
0x18002519c  jz      short loc_1800251E6
0x18002519e  sub     ecx, 1
0x1800251a1  jz      short loc_1800251D0
0x1800251a3  cmp     ecx, 1
0x1800251a6  jz      short loc_1800251BA
0x1800251a8  mov     ebx, 57h ; 'W'
0x1800251ad  mov     [rbp+arg_10], 0
0x1800251b5  xor     r13d, r13d
0x1800251b8  jmp     short loc_180025239
0x1800251ba  mov     rax, cs:?g_pAntiSpywareManager@WscServiceUtils@@3PEAVCAntiSpywareManager@@EA; CAntiSpywareManager * WscServiceUtils::g_pAntiSpywareManager
0x1800251c1  mov     r13d, 8
0x1800251c7  mov     r8, cs:?g_pAntiSpywareVerificationManager@WscServiceUtils@@3PEAVCSecurityVerificationManagerAs@@EA; CSecurityVerificationManagerAs * WscServiceUtils::g_pAntiSpywareVerificationManager
0x1800251ce  jmp     short loc_1800251FA
0x1800251d0  mov     rax, cs:?g_pFirewallManager@WscServiceUtils@@3PEAVCFirewallManager@@EA; CFirewallManager * WscServiceUtils::g_pFirewallManager
0x1800251d7  mov     r13d, 2
0x1800251dd  mov     r8, cs:?g_pFirewallVerificationManager@WscServiceUtils@@3PEAVCSecurityVerificationManagerFw@@EA; CSecurityVerificationManagerFw * WscServiceUtils::g_pFirewallVerificationManager
0x1800251e4  jmp     short loc_1800251FA
0x1800251e6  mov     rax, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; CAntiVirusManager * WscServiceUtils::g_pAntiVirusManager
0x1800251ed  mov     r13d, 1
0x1800251f3  mov     r8, cs:?g_pAntiVirusVerificationManager@WscServiceUtils@@3PEAVCSecurityVerificationManagerAv@@EA; struct CThirdPartyManager *
0x1800251fa  lea     r9, [rbp+arg_18]; struct CSecurityVerificationManager *
0x1800251fe  mov     [rbp+arg_10], rax
0x180025202  mov     rdx, rax; void *
0x180025205  mov     rcx, rbx; ClientBinding
0x180025208  call    ?CreateExternalBaseFromCaller@WscServiceUtils@@YAJPEAXPEAVCThirdPartyManager@@PEAVCSecurityVerificationManager@@PEAPEAVCExternalBase@@@Z; WscServiceUtils::CreateExternalBaseFromCaller(void *,CThirdPartyManager *,CSecurityVerificationManager *,CExternalBase * *)
0x18002520d  mov     ebx, eax
0x18002520f  test    eax, eax
0x180025211  jz      short loc_18002523C
0x180025213  mov     rcx, cs:WPP_GLOBAL_Control
0x18002521a  cmp     rcx, r14
0x18002521d  jz      short loc_180025239
0x18002521f  test    byte ptr [rcx+1Ch], 1
0x180025223  jz      short loc_180025239
0x180025225  mov     rcx, [rcx+10h]
0x180025229  mov     edx, 0D5h
0x18002522e  mov     r9d, eax
0x180025231  mov     r8, r12
0x180025234  call    WPP_SF_d
0x180025239  mov     r15d, ebx
0x18002523c  mov     dl, 1
0x18002523e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl(void)'::`2'::impl
0x180025245  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002524a  mov     rcx, [rbp+arg_18]; this
0x18002524e  call    ?CleanupAMPPLDataFromWMI@AMPPLWmiDataUtils@@YAJPEAVCExternalBase@@@Z; AMPPLWmiDataUtils::CleanupAMPPLDataFromWMI(CExternalBase *)
0x180025253  test    r15d, r15d
0x180025256  jnz     loc_180025439
0x18002525c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025263  lea     rdx, aAs; "AS"
0x18002526a  cmp     rcx, r14
0x18002526d  jz      short loc_1800252BB
0x18002526f  test    byte ptr [rcx+1Ch], 4
0x180025273  jz      short loc_1800252BB
0x180025275  mov     rax, [rbp+arg_18]
0x180025279  lea     r8, aUnknown_0; "Unknown"
0x180025280  cmp     qword ptr [rax+10h], 0
0x180025285  cmovnz  r8, [rax+10h]
0x18002528a  test    esi, esi
0x18002528c  jnz     short loc_180025297
0x18002528e  lea     r9, aAv; "AV"
0x180025295  jmp     short loc_1800252A5
0x180025297  cmp     esi, 1
0x18002529a  lea     r9, aFw; "FW"
0x1800252a1  cmovnz  r9, rdx
0x1800252a5  mov     rcx, [rcx+10h]
0x1800252a9  mov     edx, 0D6h
0x1800252ae  mov     [rsp+40h+var_20], r8
0x1800252b3  mov     r8, r12
0x1800252b6  call    WPP_SF_SS
0x1800252bb  mov     r15, [rbp+arg_10]
0x1800252bf  mov     rdx, [rbp+arg_18]; struct CExternalBase *
0x1800252c3  mov     rcx, r15; this
0x1800252c6  mov     [rbp+var_10], 0
0x1800252ce  call    ?RemoveExternalProduct@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::RemoveExternalProduct(CExternalBase *)
0x1800252d3  mov     rcx, r15; this
0x1800252d6  mov     [rbp+arg_8], eax
0x1800252d9  call    ?IsAlerted@CThirdPartyManager@@QEAAHXZ; CThirdPartyManager::IsAlerted(void)
0x1800252de  mov     rcx, cs:?g_pAlertStatus@@3PEAVCAlertStatus@@EA; lpCriticalSection
0x1800252e5  mov     r8d, eax; int
0x1800252e8  mov     edx, r13d; unsigned int
0x1800252eb  call    ?SetComponentAlerted@CAlertStatus@@QEAAJKH@Z; CAlertStatus::SetComponentAlerted(ulong,int)
0x1800252f0  mov     eax, [rbp+arg_8]
0x1800252f3  test    eax, eax
0x1800252f5  js      loc_18002545C
0x1800252fb  mov     rcx, cs:?g_pWmiEventManagerAvFw@@3PEAVCWmiEventManagerAvFw@@EA; this
0x180025302  test    rcx, rcx
0x180025305  jz      loc_1800253BB
0x18002530b  lea     r8, [rbp+var_10]; struct IWbemServices **
0x18002530f  call    ?GetWbemServices@CWmiEventManager@@QEAAJHPEAPEAUIWbemServices@@@Z; CWmiEventManager::GetWbemServices(int,IWbemServices * *)
0x180025314  mov     r15d, eax
0x180025317  test    eax, eax
0x180025319  js      short loc_180025393
0x18002531b  mov     r13, [rbp+var_10]
0x18002531f  mov     r8d, esi; enum _SECURITY_PRODUCT_TYPE
0x180025322  mov     rcx, [rbp+arg_18]; this
0x180025326  mov     rdx, r13; struct IWbemServices *
0x180025329  call    ?RemoveFromPersistentStore@CExternalBase@@QEAAJPEAUIWbemServices@@W4_SECURITY_PRODUCT_TYPE@@@Z; CExternalBase::RemoveFromPersistentStore(IWbemServices *,_SECURITY_PRODUCT_TYPE)
0x18002532e  mov     r15d, eax
0x180025331  test    eax, eax
0x180025333  jns     short loc_18002535B
0x180025335  mov     rcx, cs:WPP_GLOBAL_Control
0x18002533c  cmp     rcx, r14
0x18002533f  jz      short loc_18002535B
0x180025341  test    byte ptr [rcx+1Ch], 1
0x180025345  jz      short loc_18002535B
0x180025347  mov     rcx, [rcx+10h]
0x18002534b  mov     edx, 0D7h
0x180025350  mov     r9d, eax
0x180025353  mov     r8, r12
0x180025356  call    WPP_SF_d
0x18002535b  mov     rax, [r13+0]
0x18002535f  mov     rcx, r13
0x180025362  mov     rax, [rax+10h]
0x180025366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002536b  mov     r8, cs:?g_pFirewallManager@WscServiceUtils@@3PEAVCFirewallManager@@EA; struct CFirewallManager *
0x180025372  mov     rdx, cs:?g_pAntiSpywareManager@WscServiceUtils@@3PEAVCAntiSpywareManager@@EA; struct CAntiSpywareManager *
0x180025379  mov     rcx, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; this
0x180025380  call    ?SetThirdPartyStatus@SqmHelper@@SAJPEAVCAntiVirusManager@@PEAVCAntiSpywareManager@@PEAVCFirewallManager@@@Z; SqmHelper::SetThirdPartyStatus(CAntiVirusManager *,CAntiSpywareManager *,CFirewallManager *)
0x180025385  test    r15d, r15d
0x180025388  js      short loc_180025393
0x18002538a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025391  jmp     short loc_1800253EA
0x180025393  mov     rcx, cs:WPP_GLOBAL_Control
0x18002539a  cmp     rcx, r14
0x18002539d  jz      short loc_1800253E5
0x18002539f  test    byte ptr [rcx+1Ch], 1
0x1800253a3  jz      short loc_1800253E5
0x1800253a5  mov     rcx, [rcx+10h]
0x1800253a9  mov     edx, 0D8h
0x1800253ae  mov     r9d, r15d
0x1800253b1  mov     r8, r12
0x1800253b4  call    WPP_SF_d
0x1800253b9  jmp     short loc_1800253DE
0x1800253bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800253c2  cmp     rcx, r14
0x1800253c5  jz      short loc_1800253E5
0x1800253c7  test    byte ptr [rcx+1Ch], 1
0x1800253cb  jz      short loc_1800253E5
0x1800253cd  mov     rcx, [rcx+10h]
0x1800253d1  mov     edx, 0D9h
0x1800253d6  mov     r8, r12
0x1800253d9  call    WPP_SF_
0x1800253de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800253e5  mov     ebx, 467h
0x1800253ea  cmp     rcx, r14
0x1800253ed  jz      short loc_18002542B
0x1800253ef  test    byte ptr [rcx+1Ch], 4
0x1800253f3  jz      short loc_18002542B
0x1800253f5  test    esi, esi
0x1800253f7  jnz     short loc_180025402
0x1800253f9  lea     rax, aAv; "AV"
0x180025400  jmp     short loc_180025417
0x180025402  cmp     esi, 1
0x180025405  lea     rax, aFw; "FW"
0x18002540c  lea     rdx, aAs; "AS"
0x180025413  cmovnz  rax, rdx
0x180025417  mov     rcx, [rcx+10h]
0x18002541b  mov     edx, 0DAh
0x180025420  mov     r9, rax
0x180025423  mov     r8, r12
0x180025426  call    WPP_SF_S
0x18002542b  mov     rcx, cs:?g_pAlertStatus@@3PEAVCAlertStatus@@EA; lpCriticalSection
0x180025432  xor     edx, edx; int
0x180025434  call    ?FireNotificationEvents@CAlertStatus@@QEAAXH@Z; CAlertStatus::FireNotificationEvents(int)
0x180025439  mov     r15, [rbp+arg_10]
0x18002543d  call    ?WscDSA_FeatureIsEnabled@@YAHXZ; WscDSA_FeatureIsEnabled(void)
0x180025442  test    eax, eax
0x180025444  jz      short loc_180025489
0x180025446  test    ebx, ebx
0x180025448  jnz     short loc_180025489
0x18002544a  test    esi, esi
0x18002544c  jnz     short loc_180025489
0x18002544e  mov     r8, [rbp+arg_18]; struct CExternalBase *
0x180025452  mov     rdx, r15; struct CThirdPartyManager *
0x180025455  call    ?WscDSA_UnregisterCallback@@YAJPEAVCWmiEventManagerAvFw@@PEAVCThirdPartyManager@@PEAVCExternalBase@@@Z; WscDSA_UnregisterCallback(CWmiEventManagerAvFw *,CThirdPartyManager *,CExternalBase *)
0x18002545a  jmp     short loc_1800254A5
0x18002545c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025463  cmp     rcx, r14
0x180025466  jz      short loc_180025482
0x180025468  test    byte ptr [rcx+1Ch], 1
0x18002546c  jz      short loc_180025482
0x18002546e  mov     rcx, [rcx+10h]
0x180025472  mov     edx, 0DBh
0x180025477  mov     r9d, eax
0x18002547a  mov     r8, r12
0x18002547d  call    WPP_SF_d
0x180025482  mov     ebx, 2
0x180025487  jmp     short loc_18002543D
0x180025489  call    ?WscDSA_FeatureIsEnabled@@YAHXZ; WscDSA_FeatureIsEnabled(void)
0x18002548e  test    eax, eax
0x180025490  jnz     short loc_1800254A5
0x180025492  test    ebx, ebx
0x180025494  jnz     short loc_1800254A5
0x180025496  test    esi, esi
0x180025498  jnz     short loc_1800254A5
0x18002549a  lea     edx, [rax+3]; unsigned int
0x18002549d  lea     ecx, [rax+1]; this
0x1800254a0  call    ?SetDefenderStatus@@YAJHK@Z; SetDefenderStatus(int,ulong)
0x1800254a5  mov     rcx, [rbp+arg_18]
0x1800254a9  test    rcx, rcx
0x1800254ac  jz      short loc_1800254D5
0x1800254ae  test    ebx, ebx
0x1800254b0  jnz     short loc_1800254C0
0x1800254b2  mov     rdx, rcx; struct CExternalBase *
0x1800254b5  mov     ecx, esi; enum _SECURITY_PRODUCT_TYPE
0x1800254b7  call    ?WscTelemetryEventWriteProductDeregistration@@YAXW4_SECURITY_PRODUCT_TYPE@@PEAVCExternalBase@@@Z; WscTelemetryEventWriteProductDeregistration(_SECURITY_PRODUCT_TYPE,CExternalBase *)
0x1800254bc  mov     rcx, [rbp+arg_18]
0x1800254c0  test    rcx, rcx
0x1800254c3  jz      short loc_1800254D5
0x1800254c5  mov     rax, [rcx]
0x1800254c8  mov     edx, 1
0x1800254cd  mov     rax, [rax]
0x1800254d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254dc  cmp     rcx, r14
0x1800254df  jz      short loc_1800254FB
0x1800254e1  test    byte ptr [rcx+1Ch], 8
0x1800254e5  jz      short loc_1800254FB
0x1800254e7  mov     rcx, [rcx+10h]
0x1800254eb  mov     edx, 0DCh
0x1800254f0  mov     r9d, ebx
0x1800254f3  mov     r8, r12
0x1800254f6  call    WPP_SF_d
0x1800254fb  mov     eax, ebx
0x1800254fd  add     rsp, 40h
0x180025501  pop     r15
0x180025503  pop     r14
0x180025505  pop     r13
0x180025507  pop     r12
0x180025509  pop     rsi
0x18002550a  pop     rbx
0x18002550b  pop     rbp
0x18002550c  retn
```
