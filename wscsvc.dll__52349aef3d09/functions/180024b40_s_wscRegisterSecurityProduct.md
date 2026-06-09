# s_wscRegisterSecurityProduct

- ea: `0x180024b40`
- end: `0x1800250ab`
- name: `s_wscRegisterSecurityProduct`
- size: `1387`
- prototype: `__int64 __fastcall(void *, enum _SECURITY_PRODUCT_TYPE, unsigned __int16 *, unsigned __int16 *, int, int)`
- caller_count: `0`
- callee_count: `21`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180002e30`
- `0x180008910`
- `0x180008e48`
- `0x180015bf0`
- `0x180018b60`
- `0x1800191c0`
- `0x180019850`
- `0x18001c4c0`
- `0x18001c6dc`
- `0x18001fdd8`
- `0x1800202e8`
- `0x180024b40`
- `0x1800250c0`
- `0x1800281c4`
- `0x180029158`
- `0x180031cd0`
- `0x180031efc`
- `0x1800321f0`
- `0x180032ef4`
- `0x180035518`
- `0x180042010`

## string_xrefs

- `0x180024bd5`: `s_wscRegisterSecurityProduct`

## pseudocode

```c
__int64 __fastcall s_wscRegisterSecurityProduct(
        void *a1,
        enum _SECURITY_PRODUCT_TYPE a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int a5,
        int a6)
{
  int v9; // r14d
  int v10; // eax
  void *v11; // r8
  int v12; // ebx
  CThirdPartyManager *v13; // rax
  struct CThirdPartyManager *v14; // r8
  unsigned int ExternalBaseFromCaller; // eax
  CThirdPartyManager *v16; // rcx
  CExternalBase *v17; // rcx
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdx
  int v21; // edx
  CThirdPartyManager *v22; // r12
  int updated; // eax
  int v24; // r14d
  int IsAlerted; // eax
  int v26; // edx
  int WbemServices; // r14d
  struct IWbemServices *v28; // r12
  int v29; // eax
  CThirdPartyManager *v30; // rcx
  const wchar_t *v31; // rax
  const wchar_t *v32; // rax
  struct CExternalBase **v33; // [rsp+20h] [rbp-40h]
  struct IWbemServices *v34; // [rsp+40h] [rbp-20h] BYREF
  CThirdPartyManager *v35; // [rsp+48h] [rbp-18h] BYREF
  CExternalBase *v36; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v37; // [rsp+A8h] [rbp+48h]

  v36 = 0;
  LODWORD(v35) = 0;
  LODWORD(v34) = 0;
  v37 = 2;
  if ( a2 == SECURITY_PRODUCT_TYPE_ANTISPYWARE )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
    }
    return 0;
  }
  v9 = 0;
  if ( a2 )
  {
    if ( a2 != SECURITY_PRODUCT_TYPE_FIREWALL )
    {
      v12 = 87;
      goto LABEL_79;
    }
    v13 = WscServiceUtils::g_pFirewallManager;
    v14 = WscServiceUtils::g_pFirewallVerificationManager;
  }
  else
  {
    v10 = ValidateCallerAMPPL((int *)&v34, (int *)&v35, a1, L"s_wscRegisterSecurityProduct", a3, a4);
    v9 = v10;
    if ( v10 >= 0 )
    {
      WscServiceUtils::CheckAndAddNonCompliantProduct((WscServiceUtils *)(unsigned int)v34, (int)a1, v11);
      v12 = (int)v35;
    }
    else
    {
      v12 = (unsigned __int16)v10;
    }
    if ( v12 )
    {
      WppLogUnregisterNonCompliantProduct(a1);
      s_wscUnregisterSecurityProduct(a1, SECURITY_PRODUCT_TYPE_ANTIVIRUS);
LABEL_79:
      v16 = WPP_GLOBAL_Control;
      goto LABEL_80;
    }
    v13 = WscServiceUtils::g_pAntiVirusManager;
    v14 = WscServiceUtils::g_pAntiVirusVerificationManager;
    v37 = 1;
  }
  v35 = v13;
  ExternalBaseFromCaller = WscServiceUtils::CreateExternalBaseFromCaller(
                             a1,
                             v13,
                             v14,
                             (struct CSecurityVerificationManager *)&v36,
                             v33);
  v12 = ExternalBaseFromCaller;
  if ( ExternalBaseFromCaller )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_80;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      199,
      WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
      ExternalBaseFromCaller);
    goto LABEL_79;
  }
  v17 = v36;
  *((_DWORD *)v36 + 20) &= 0xFFF0FFFF;
  v18 = (a5 != 0 ? 327680 : 0x40000) | 0x20000;
  if ( !a6 )
    v18 = a5 != 0 ? 327680 : 0x40000;
  *((_DWORD *)v17 + 20) |= v18;
  if ( !a3 || !*a3 )
  {
    v12 = 87;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 201, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
    if ( v9 < 0 )
      goto LABEL_35;
    goto LABEL_61;
  }
  v19 = CExternalBase::SetPath(v36, a3);
  LOWORD(v9) = v19;
  if ( v19 < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_35;
    }
    v20 = 200;
LABEL_34:
    WPP_SF_d(*((_QWORD *)v16 + 2), v20, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, (unsigned int)v19);
    v16 = WPP_GLOBAL_Control;
LABEL_35:
    v12 = (unsigned __int16)v9;
    goto LABEL_36;
  }
  v21 = (int)a4;
  v16 = WPP_GLOBAL_Control;
  if ( a4 && *a4 )
  {
    v19 = CExternalBase::SetDisplayName(v36, a4);
    LOWORD(v9) = v19;
    if ( v19 < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_35;
      }
      v20 = 202;
      goto LABEL_34;
    }
    goto LABEL_60;
  }
  v12 = 87;
  if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control )
    goto LABEL_36;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 203, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
LABEL_60:
    v16 = WPP_GLOBAL_Control;
LABEL_61:
    v21 = (int)a4;
  }
  if ( v16 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
  {
    if ( a2 )
      v31 = L"FW";
    else
      v31 = L"AV";
    WPP_SF_SSdd(*((_QWORD *)v16 + 2), v21, a6, v21, (__int64)v31, a5, a6);
    v16 = WPP_GLOBAL_Control;
  }
LABEL_36:
  if ( !v12 )
  {
    v22 = v35;
    v34 = 0;
    updated = CThirdPartyManager::UpdateExternalProduct(v35, v36);
    v24 = updated;
    if ( updated < 0
      && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        205,
        WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
        (unsigned int)updated);
    }
    IsAlerted = CThirdPartyManager::IsAlerted(v22);
    CAlertStatus::SetComponentAlerted(g_pAlertStatus, v37, IsAlerted);
    if ( v24 < 0 )
      goto LABEL_79;
    if ( g_pWmiEventManagerAvFw )
    {
      WbemServices = CWmiEventManager::GetWbemServices(g_pWmiEventManagerAvFw, v26, &v34);
      if ( WbemServices >= 0 )
      {
        v28 = v34;
        v29 = CExternalBase::UpdatePersistentStore(v36, v34, (unsigned int)a2, 0xFFFFFFFFLL);
        WbemServices = v29;
        if ( v29 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            206,
            WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
            (unsigned int)v29);
        }
        ((void (__fastcall *)(struct IWbemServices *))v28->lpVtbl->Release)(v28);
        SqmHelper::SetThirdPartyStatus(
          WscServiceUtils::g_pAntiVirusManager,
          WscServiceUtils::g_pAntiSpywareManager,
          WscServiceUtils::g_pFirewallManager);
        if ( WbemServices >= 0 )
          goto LABEL_71;
      }
      v12 = 1127;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            207,
            WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
            (unsigned int)WbemServices);
LABEL_71:
          v30 = WPP_GLOBAL_Control;
          goto LABEL_72;
        }
        goto LABEL_72;
      }
    }
    else
    {
      v12 = 1127;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 208, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, 1127);
          goto LABEL_71;
        }
LABEL_72:
        if ( v30 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 0x10) != 0 )
        {
          if ( a2 )
            v32 = L"FW";
          else
            v32 = L"AV";
          WPP_SF_S(*((_QWORD *)v30 + 2), 209, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v32);
        }
      }
    }
    CAlertStatus::FireNotificationEvents(g_pAlertStatus, 0);
    goto LABEL_79;
  }
LABEL_80:
  if ( v36 )
  {
    if ( v12 >= 0 )
    {
      WscTelemetryEventWriteProductRegistration(a2, v36);
      v16 = WPP_GLOBAL_Control;
    }
    if ( v36 )
    {
      (**(void (__fastcall ***)(CExternalBase *, __int64))v36)(v36, 1);
      v16 = WPP_GLOBAL_Control;
    }
  }
  if ( v16 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v16 + 2), 210, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180024b40  mov     [rsp-38h+arg_18], r9
0x180024b45  mov     [rsp-38h+arg_10], r8
0x180024b4a  push    rbp
0x180024b4b  push    rbx
0x180024b4c  push    rsi
0x180024b4d  push    r12
0x180024b4f  push    r13
0x180024b51  push    r14
0x180024b53  push    r15
0x180024b55  mov     rbp, rsp
0x180024b58  sub     rsp, 60h
0x180024b5c  xor     r10d, r10d
0x180024b5f  mov     r13d, edx
0x180024b62  mov     r12, rcx
0x180024b65  mov     [rbp+var_10], r10
0x180024b69  mov     dword ptr [rbp+var_18], r10d
0x180024b6d  mov     dword ptr [rbp+var_20], r10d
0x180024b71  lea     eax, [r10+2]
0x180024b75  mov     [rbp+arg_8], eax
0x180024b78  cmp     edx, eax
0x180024b7a  jnz     short loc_180024BB1
0x180024b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b83  lea     rsi, WPP_GLOBAL_Control
0x180024b8a  cmp     rcx, rsi
0x180024b8d  jz      short loc_180024BAA
0x180024b8f  test    byte ptr [rcx+1Ch], 1
0x180024b93  jz      short loc_180024BAA
0x180024b95  mov     rcx, [rcx+10h]
0x180024b99  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180024ba0  mov     edx, 0C6h
0x180024ba5  call    WPP_SF_
0x180024baa  xor     eax, eax
0x180024bac  jmp     loc_18002509B
0x180024bb1  lea     rsi, WPP_GLOBAL_Control
0x180024bb8  mov     r14d, r10d
0x180024bbb  lea     r15, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180024bc2  test    r13d, r13d
0x180024bc5  jnz     short loc_180024C1D
0x180024bc7  mov     [rsp+60h+var_38], r9; unsigned __int16 *
0x180024bcc  lea     rdx, [rbp+var_18]; int *
0x180024bd0  mov     [rsp+60h+var_40], r8; struct CExternalBase **
0x180024bd5  lea     r9, aSWscregisterse; "s_wscRegisterSecurityProduct"
0x180024bdc  mov     r8, r12; void *
0x180024bdf  lea     rcx, [rbp+var_20]; int *
0x180024be3  call    ?ValidateCallerAMPPL@@YAJPEAJ0PEAXPEBG22@Z; ValidateCallerAMPPL(long *,long *,void *,ushort const *,ushort const *,ushort const *)
0x180024be8  mov     r14d, eax
0x180024beb  test    eax, eax
0x180024bed  jns     short loc_180024BF4
0x180024bef  movzx   ebx, ax
0x180024bf2  jmp     short loc_180024C02
0x180024bf4  mov     ecx, dword ptr [rbp+var_20]; this
0x180024bf7  mov     rdx, r12; int
0x180024bfa  call    ?CheckAndAddNonCompliantProduct@WscServiceUtils@@YAJJPEAX@Z; WscServiceUtils::CheckAndAddNonCompliantProduct(long,void *)
0x180024bff  mov     ebx, dword ptr [rbp+var_18]
0x180024c02  test    ebx, ebx
0x180024c04  jz      short loc_180024C60
0x180024c06  mov     rcx, r12; void *
0x180024c09  call    ?WppLogUnregisterNonCompliantProduct@@YAJPEAX@Z; WppLogUnregisterNonCompliantProduct(void *)
0x180024c0e  xor     edx, edx; enum _SECURITY_PRODUCT_TYPE
0x180024c10  mov     rcx, r12; void *
0x180024c13  call    s_wscUnregisterSecurityProduct
0x180024c18  jmp     loc_180025034
0x180024c1d  mov     ecx, r13d
0x180024c20  test    r13d, r13d
0x180024c23  jz      short loc_180024C60
0x180024c25  sub     ecx, 1
0x180024c28  jz      short loc_180024C50
0x180024c2a  cmp     ecx, 1
0x180024c2d  jz      short loc_180024C39
0x180024c2f  mov     ebx, 57h ; 'W'
0x180024c34  jmp     loc_180025034
0x180024c39  mov     rax, cs:?g_pAntiSpywareManager@WscServiceUtils@@3PEAVCAntiSpywareManager@@EA; CAntiSpywareManager * WscServiceUtils::g_pAntiSpywareManager
0x180024c40  mov     r8, cs:?g_pAntiSpywareVerificationManager@WscServiceUtils@@3PEAVCSecurityVerificationManagerAs@@EA; CSecurityVerificationManagerAs * WscServiceUtils::g_pAntiSpywareVerificationManager
0x180024c47  mov     [rbp+arg_8], 8
0x180024c4e  jmp     short loc_180024C75
0x180024c50  mov     rax, cs:?g_pFirewallManager@WscServiceUtils@@3PEAVCFirewallManager@@EA; CFirewallManager * WscServiceUtils::g_pFirewallManager
0x180024c57  mov     r8, cs:?g_pFirewallVerificationManager@WscServiceUtils@@3PEAVCSecurityVerificationManagerFw@@EA; CSecurityVerificationManagerFw * WscServiceUtils::g_pFirewallVerificationManager
0x180024c5e  jmp     short loc_180024C75
0x180024c60  mov     rax, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; CAntiVirusManager * WscServiceUtils::g_pAntiVirusManager
0x180024c67  mov     r8, cs:?g_pAntiVirusVerificationManager@WscServiceUtils@@3PEAVCSecurityVerificationManagerAv@@EA; struct CThirdPartyManager *
0x180024c6e  mov     [rbp+arg_8], 1
0x180024c75  lea     r9, [rbp+var_10]; struct CSecurityVerificationManager *
0x180024c79  mov     [rbp+var_18], rax
0x180024c7d  mov     rdx, rax; void *
0x180024c80  mov     rcx, r12; ClientBinding
0x180024c83  call    ?CreateExternalBaseFromCaller@WscServiceUtils@@YAJPEAXPEAVCThirdPartyManager@@PEAVCSecurityVerificationManager@@PEAPEAVCExternalBase@@@Z; WscServiceUtils::CreateExternalBaseFromCaller(void *,CThirdPartyManager *,CSecurityVerificationManager *,CExternalBase * *)
0x180024c88  xor     r10d, r10d
0x180024c8b  mov     ebx, eax
0x180024c8d  test    eax, eax
0x180024c8f  jz      short loc_180024CC4
0x180024c91  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c98  cmp     rcx, rsi
0x180024c9b  jz      loc_18002503B
0x180024ca1  test    byte ptr [rcx+1Ch], 1
0x180024ca5  jz      loc_18002503B
0x180024cab  mov     rcx, [rcx+10h]
0x180024caf  mov     edx, 0C7h
0x180024cb4  mov     r9d, eax
0x180024cb7  mov     r8, r15
0x180024cba  call    WPP_SF_d
0x180024cbf  jmp     loc_180025034
0x180024cc4  mov     rcx, [rbp+var_10]
0x180024cc8  mov     r12d, [rbp+arg_20]
0x180024ccc  mov     eax, r12d
0x180024ccf  neg     eax
0x180024cd1  sbb     edx, edx
0x180024cd3  and     dword ptr [rcx+50h], 0FFF0FFFFh
0x180024cda  and     edx, 10000h
0x180024ce0  add     edx, 40000h
0x180024ce6  mov     eax, edx
0x180024ce8  bts     eax, 11h
0x180024cec  cmp     [rbp+arg_28], r10d
0x180024cf0  cmovz   eax, edx
0x180024cf3  or      [rcx+50h], eax
0x180024cf6  mov     rax, [rbp+arg_10]
0x180024cfa  test    rax, rax
0x180024cfd  jz      loc_180024EE0
0x180024d03  cmp     [rax], r10w
0x180024d07  jz      loc_180024EE0
0x180024d0d  mov     rcx, [rbp+var_10]; this
0x180024d11  mov     rdx, rax; unsigned __int16 *
0x180024d14  call    ?SetPath@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetPath(ushort const *)
0x180024d19  xor     r10d, r10d
0x180024d1c  mov     r14d, eax
0x180024d1f  test    eax, eax
0x180024d21  jns     short loc_180024D3C
0x180024d23  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d2a  cmp     rcx, rsi
0x180024d2d  jz      short loc_180024DA1
0x180024d2f  test    byte ptr [rcx+1Ch], 1
0x180024d33  jz      short loc_180024DA1
0x180024d35  mov     edx, 0C8h
0x180024d3a  jmp     short loc_180024D88
0x180024d3c  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x180024d40  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d47  test    rdx, rdx
0x180024d4a  jz      loc_180024F1B
0x180024d50  cmp     [rdx], r10w
0x180024d54  jz      loc_180024F1B
0x180024d5a  mov     rcx, [rbp+var_10]; this
0x180024d5e  call    ?SetDisplayName@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetDisplayName(ushort const *)
0x180024d63  xor     r10d, r10d
0x180024d66  mov     r14d, eax
0x180024d69  test    eax, eax
0x180024d6b  jns     loc_180024F41
0x180024d71  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d78  cmp     rcx, rsi
0x180024d7b  jz      short loc_180024DA1
0x180024d7d  test    byte ptr [rcx+1Ch], 1
0x180024d81  jz      short loc_180024DA1
0x180024d83  mov     edx, 0CAh
0x180024d88  mov     rcx, [rcx+10h]
0x180024d8c  mov     r9d, eax
0x180024d8f  mov     r8, r15
0x180024d92  call    WPP_SF_d
0x180024d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d9e  xor     r10d, r10d
0x180024da1  movzx   ebx, r14w
0x180024da5  test    ebx, ebx
0x180024da7  jnz     loc_18002503B
0x180024dad  mov     r12, [rbp+var_18]
0x180024db1  mov     rdx, [rbp+var_10]; struct CExternalBase *
0x180024db5  mov     rcx, r12; this
0x180024db8  mov     [rbp+var_20], r10
0x180024dbc  call    ?UpdateExternalProduct@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::UpdateExternalProduct(CExternalBase *)
0x180024dc1  mov     r14d, eax
0x180024dc4  test    eax, eax
0x180024dc6  jns     short loc_180024DEE
0x180024dc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180024dcf  cmp     rcx, rsi
0x180024dd2  jz      short loc_180024DEE
0x180024dd4  test    byte ptr [rcx+1Ch], 1
0x180024dd8  jz      short loc_180024DEE
0x180024dda  mov     rcx, [rcx+10h]
0x180024dde  mov     edx, 0CDh
0x180024de3  mov     r9d, eax
0x180024de6  mov     r8, r15
0x180024de9  call    WPP_SF_d
0x180024dee  mov     rcx, r12; this
0x180024df1  call    ?IsAlerted@CThirdPartyManager@@QEAAHXZ; CThirdPartyManager::IsAlerted(void)
0x180024df6  mov     edx, [rbp+arg_8]; unsigned int
0x180024df9  mov     r8d, eax; int
0x180024dfc  mov     rcx, cs:?g_pAlertStatus@@3PEAVCAlertStatus@@EA; lpCriticalSection
0x180024e03  call    ?SetComponentAlerted@CAlertStatus@@QEAAJKH@Z; CAlertStatus::SetComponentAlerted(ulong,int)
0x180024e08  test    r14d, r14d
0x180024e0b  js      loc_180025034
0x180024e11  mov     rcx, cs:?g_pWmiEventManagerAvFw@@3PEAVCWmiEventManagerAvFw@@EA; this
0x180024e18  test    rcx, rcx
0x180024e1b  jz      loc_180024FB1
0x180024e21  lea     r8, [rbp+var_20]; struct IWbemServices **
0x180024e25  call    ?GetWbemServices@CWmiEventManager@@QEAAJHPEAPEAUIWbemServices@@@Z; CWmiEventManager::GetWbemServices(int,IWbemServices * *)
0x180024e2a  mov     r14d, eax
0x180024e2d  test    eax, eax
0x180024e2f  js      short loc_180024EA8
0x180024e31  mov     r12, [rbp+var_20]
0x180024e35  or      r9d, 0FFFFFFFFh
0x180024e39  mov     rcx, [rbp+var_10]
0x180024e3d  mov     rdx, r12
0x180024e40  mov     r8d, r13d
0x180024e43  call    ?UpdatePersistentStore@CExternalBase@@QEAAJPEAUIWbemServices@@W4_SECURITY_PRODUCT_TYPE@@W4_DATASTORE_BITMASK@@@Z; CExternalBase::UpdatePersistentStore(IWbemServices *,_SECURITY_PRODUCT_TYPE,_DATASTORE_BITMASK)
0x180024e48  mov     r14d, eax
0x180024e4b  test    eax, eax
0x180024e4d  jns     short loc_180024E75
0x180024e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e56  cmp     rcx, rsi
0x180024e59  jz      short loc_180024E75
0x180024e5b  test    byte ptr [rcx+1Ch], 1
0x180024e5f  jz      short loc_180024E75
0x180024e61  mov     rcx, [rcx+10h]
0x180024e65  mov     edx, 0CEh
0x180024e6a  mov     r9d, eax
0x180024e6d  mov     r8, r15
0x180024e70  call    WPP_SF_d
0x180024e75  mov     rax, [r12]
0x180024e79  mov     rcx, r12
0x180024e7c  mov     rax, [rax+10h]
0x180024e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e85  mov     r8, cs:?g_pFirewallManager@WscServiceUtils@@3PEAVCFirewallManager@@EA; struct CFirewallManager *
0x180024e8c  mov     rdx, cs:?g_pAntiSpywareManager@WscServiceUtils@@3PEAVCAntiSpywareManager@@EA; struct CAntiSpywareManager *
0x180024e93  mov     rcx, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; this
0x180024e9a  call    ?SetThirdPartyStatus@SqmHelper@@SAJPEAVCAntiVirusManager@@PEAVCAntiSpywareManager@@PEAVCFirewallManager@@@Z; SqmHelper::SetThirdPartyStatus(CAntiVirusManager *,CAntiSpywareManager *,CFirewallManager *)
0x180024e9f  test    r14d, r14d
0x180024ea2  jns     loc_180024FDC
0x180024ea8  mov     ebx, 467h
0x180024ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180024eb4  cmp     rcx, rsi
0x180024eb7  jz      loc_180025026
0x180024ebd  test    byte ptr [rcx+1Ch], 1
0x180024ec1  jz      loc_180024FE3
0x180024ec7  mov     rcx, [rcx+10h]
0x180024ecb  mov     edx, 0CFh
0x180024ed0  mov     r9d, r14d
0x180024ed3  mov     r8, r15
0x180024ed6  call    WPP_SF_d
0x180024edb  jmp     loc_180024FDC
0x180024ee0  mov     ebx, 57h ; 'W'
0x180024ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x180024eec  cmp     rcx, rsi
0x180024eef  jz      short loc_180024F10
0x180024ef1  test    byte ptr [rcx+1Ch], 1
0x180024ef5  jz      short loc_180024F10
0x180024ef7  mov     rcx, [rcx+10h]
0x180024efb  lea     edx, [rbx+72h]
0x180024efe  mov     r8, r15
0x180024f01  call    WPP_SF_
0x180024f06  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f0d  xor     r10d, r10d
0x180024f10  test    r14d, r14d
0x180024f13  js      loc_180024DA1
0x180024f19  jmp     short loc_180024F48
0x180024f1b  mov     ebx, 57h ; 'W'
0x180024f20  cmp     rcx, rsi
0x180024f23  jz      loc_180024DA5
0x180024f29  test    byte ptr [rcx+1Ch], 1
0x180024f2d  jz      short loc_180024F4C
0x180024f2f  mov     rcx, [rcx+10h]
0x180024f33  lea     edx, [rbx+74h]
0x180024f36  mov     r8, r15
0x180024f39  call    WPP_SF_
0x180024f3e  xor     r10d, r10d
0x180024f41  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f48  mov     rdx, [rbp+arg_18]
0x180024f4c  cmp     rcx, rsi
0x180024f4f  jz      loc_180024DA5
0x180024f55  test    byte ptr [rcx+1Ch], 4
0x180024f59  jz      loc_180024DA5
0x180024f5f  test    r13d, r13d
0x180024f62  jnz     short loc_180024F6D
0x180024f64  lea     rax, aAv; "AV"
0x180024f6b  jmp     short loc_180024F83
0x180024f6d  cmp     r13d, 1
0x180024f71  lea     rax, aFw; "FW"
0x180024f78  lea     r8, aAs; "AS"
0x180024f7f  cmovnz  rax, r8
0x180024f83  mov     r8d, [rbp+arg_28]
0x180024f87  mov     r9, rdx
0x180024f8a  mov     rcx, [rcx+10h]
0x180024f8e  mov     [rsp+60h+var_30], r8d
0x180024f93  mov     dword ptr [rsp+60h+var_38], r12d
0x180024f98  mov     [rsp+60h+var_40], rax
0x180024f9d  call    WPP_SF_SSdd
0x180024fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180024fa9  xor     r10d, r10d
0x180024fac  jmp     loc_180024DA5
0x180024fb1  mov     ebx, 467h
0x180024fb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180024fbd  cmp     rcx, rsi
0x180024fc0  jz      short loc_180025026
0x180024fc2  test    byte ptr [rcx+1Ch], 1
0x180024fc6  jz      short loc_180024FE3
0x180024fc8  mov     rcx, [rcx+10h]
0x180024fcc  mov     edx, 0D0h
0x180024fd1  mov     r9d, ebx
0x180024fd4  mov     r8, r15
0x180024fd7  call    WPP_SF_d
0x180024fdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180024fe3  cmp     rcx, rsi
0x180024fe6  jz      short loc_180025026
0x180024fe8  test    byte ptr [rcx+1Ch], 10h
0x180024fec  jz      short loc_180025026
  ... truncated ...
```
