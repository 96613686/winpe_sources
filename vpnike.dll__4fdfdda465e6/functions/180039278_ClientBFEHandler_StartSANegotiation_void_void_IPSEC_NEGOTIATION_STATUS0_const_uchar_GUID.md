# ClientBFEHandler::StartSANegotiation(void (*)(void *,IPSEC_NEGOTIATION_STATUS0_ const *),uchar,_GUID)

- ea: `0x180039278`
- end: `0x180039f9f`
- name: `?StartSANegotiation@ClientBFEHandler@@QEAAKP6AXPEAXPEBUIPSEC_NEGOTIATION_STATUS0_@@@ZEU_GUID@@@Z`
- size: `3367`
- prototype: `__int64 __fastcall(ClientBFEHandler *this, void (*)(void *, const struct IPSEC_NEGOTIATION_STATUS0_ *), char, struct _GUID *)`
- caller_count: `2`
- callee_count: `21`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b9d0`
- `0x18001bd20`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18000785c`
- `0x180007894`
- `0x18000961c`
- `0x180009cf0`
- `0x18002e6f4`
- `0x180031f10`
- `0x180039278`
- `0x18003a068`
- `0x18005d9ac`
- `0x18005dd70`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x180077546`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `fwpuclnt!IPsecSaInitiateAsync0` at `0x180039cf7`
- `fwpuclnt!IPsecSaInitiateAsync0` at `0x180039cf7`
- `fwpuclnt!FwpmFreeMemory0` at `0x180039f21`
- `fwpuclnt!FwpmFreeMemory0` at `0x180039f21`
- `fwpuclnt!FwpmProviderContextGetByKey3` at `0x180039554`
- `fwpuclnt!FwpmProviderContextGetByKey3` at `0x180039554`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800397cc`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800397cc`
- `WS2_32!__imp_ntohl` at `0x1800399ff`
- `WS2_32!__imp_ntohl` at `0x180039a0f`
- `WS2_32!__imp_ntohl` at `0x1800399ff`
- `WS2_32!__imp_ntohl` at `0x180039a0f`

## string_xrefs

- `0x180039ee2`: `IKEEXT Service is not running, hence return ERROR_IPSEC_SERVICE_STOPPED`
- `0x1800399d7`: `TunnelProtocolV4`
- `0x180039b08`: `TunnelProtocolV6`

## pseudocode

```c
__int64 __fastcall ClientBFEHandler::StartSANegotiation(
        ClientBFEHandler *this,
        void (*a2)(void *, const struct IPSEC_NEGOTIATION_STATUS0_ *),
        char a3,
        struct _GUID *a4)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rcx
  int v10; // r15d
  int v11; // r12d
  unsigned int v12; // esi
  unsigned int BfeHandle; // eax
  void *v14; // r14
  PVOID *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rcx
  _QWORD *v19; // rax
  __int64 v20; // rcx
  __int128 *v21; // r9
  const wchar_t *v22; // r8
  unsigned int v23; // eax
  __int64 v24; // rax
  __int64 v25; // rax
  unsigned int v26; // eax
  __int64 v27; // r9
  int v28; // edi
  PVOID *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rax
  __int64 v35; // rax
  unsigned int v36; // eax
  PVOID *v37; // r10
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rcx
  _QWORD *v42; // rax
  __int64 v43; // rcx
  __int128 *v44; // r9
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  _QWORD *v49; // rax
  __int64 v50; // rcx
  __int128 *v51; // r9
  __int64 v52; // rcx
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rcx
  _QWORD *v57; // rax
  __int64 v58; // rcx
  __int128 *v59; // r9
  __int64 v60; // rcx
  __int64 v61; // r9
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rdx
  __int64 v65; // rcx
  _QWORD *v66; // rax
  __int64 v67; // rcx
  __int128 *v68; // r9
  unsigned int v69; // eax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rcx
  _QWORD *v74; // rax
  __int64 v75; // rcx
  __int128 *v76; // r9
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rcx
  _QWORD *v80; // rax
  unsigned int v81; // ebx
  unsigned int v83; // [rsp+40h] [rbp-C0h] BYREF
  void *p; // [rsp+48h] [rbp-B8h] BYREF
  int v85; // [rsp+50h] [rbp-B0h] BYREF
  void *v86; // [rsp+58h] [rbp-A8h] BYREF
  NET_LUID InterfaceLuid; // [rsp+60h] [rbp-A0h] BYREF
  void (*v88)(void *, const struct IPSEC_NEGOTIATION_STATUS0_ *); // [rsp+68h] [rbp-98h]
  __int64 v89; // [rsp+70h] [rbp-90h] BYREF
  __int128 v90; // [rsp+78h] [rbp-88h]
  __int128 v91; // [rsp+88h] [rbp-78h]
  __int64 v92; // [rsp+98h] [rbp-68h]
  int v93; // [rsp+A0h] [rbp-60h]
  int v94; // [rsp+A4h] [rbp-5Ch]
  _OWORD v95[3]; // [rsp+A8h] [rbp-58h] BYREF
  int v96; // [rsp+E0h] [rbp-20h] BYREF
  u_long v97; // [rsp+E4h] [rbp-1Ch]
  __int64 v98; // [rsp+E8h] [rbp-18h]
  int v99; // [rsp+F0h] [rbp-10h]
  u_long v100; // [rsp+F4h] [rbp-Ch]
  __int64 v101; // [rsp+F8h] [rbp-8h]
  int v102; // [rsp+100h] [rbp+0h]
  int v103; // [rsp+104h] [rbp+4h]
  __int64 v104; // [rsp+108h] [rbp+8h]
  NET_LUID v105; // [rsp+118h] [rbp+18h]
  int v106; // [rsp+128h] [rbp+28h]
  _OWORD *v107; // [rsp+138h] [rbp+38h]
  __int64 v108; // [rsp+140h] [rbp+40h]
  __int64 v109; // [rsp+148h] [rbp+48h]
  int v110; // [rsp+150h] [rbp+50h]
  __int64 v111; // [rsp+158h] [rbp+58h]
  __int64 v112; // [rsp+178h] [rbp+78h]
  __int128 v113; // [rsp+180h] [rbp+80h] BYREF
  int v114; // [rsp+190h] [rbp+90h] BYREF
  __int128 v115; // [rsp+194h] [rbp+94h]
  __int128 v116; // [rsp+1A4h] [rbp+A4h]
  int v117; // [rsp+1B4h] [rbp+B4h]
  _BYTE v118[272]; // [rsp+1C0h] [rbp+C0h] BYREF
  int v119; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v120[2044]; // [rsp+2D4h] [rbp+1D4h] BYREF

  v88 = a2;
  memset_0(&v96, 0, 0xA0u);
  v83 = 0;
  p = 0;
  memset(v95, 0, sizeof(v95));
  v85 = 0;
  memset_0(v118, 0, 0x102u);
  InterfaceLuid.Value = 0;
  v86 = 0;
  v9 = *(_QWORD *)(*((_QWORD *)this + 6) + 112LL);
  v10 = *(_DWORD *)(v9 + 1472);
  v11 = *(_DWORD *)(v9 + 40);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(v8) = v11 == 2;
    LOBYTE(v7) = v10 == 2;
    WPP_SF__guid_ccc(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, a4, a3 != 0, v10 == 2, v11 == 2);
  }
  v119 = 0;
  memset_0(v120, 0, sizeof(v120));
  v114 = 0;
  v115 = 0;
  v116 = 0;
  v117 = 0;
  v113 = 0;
  v90 = 0;
  v89 = 0;
  v91 = 0;
  v92 = 0;
  v12 = -1;
  v93 = -1;
  v94 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v89,
      L"ClientBFEHandler::StartSANegotiation",
      &v83,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithConnObj,
      *((void **)this + 6));
  memset_0(&v96, 0, 0xA0u);
  BfeHandle = BFEHandler::GetBfeHandle(&v86);
  v83 = BfeHandle;
  v14 = v86;
  if ( !v86 )
  {
    if ( BfeHandle )
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_14;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, BfeHandle);
    }
    v15 = (PVOID *)WPP_GLOBAL_Control;
LABEL_14:
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_210;
    LOWORD(v119) = 0;
    LOWORD(v114) = 0;
    v16 = *((_QWORD *)this + 6);
    if ( v16 )
    {
      v17 = *(_QWORD *)(v16 + 112);
      if ( v17 )
      {
        if ( *(_QWORD *)(v17 + 16) )
          v12 = *(_DWORD *)(v17 + 16);
      }
    }
    ConvertPortNoToString(&v114, v12);
    FormatRRASErrorString(&v119, L"GetBfeHandle failed: %d", v83);
LABEL_20:
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v18 = *((_QWORD *)this + 6);
      v19 = (_QWORD *)(v18 + 112);
      if ( v18 )
      {
        if ( *v19 )
          v20 = *v19 + 2686LL;
        else
          v20 = 0;
        if ( *v19 )
        {
          v21 = (__int128 *)(*v19 + 2120LL);
LABEL_29:
          v22 = (const wchar_t *)&v119;
LABEL_208:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (_DWORD)v22,
            (_DWORD)v21,
            v20,
            (__int64)&v114);
          goto LABEL_209;
        }
      }
      else
      {
        v20 = 0;
      }
      v21 = &v113;
      goto LABEL_29;
    }
LABEL_209:
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_210;
  }
  if ( !memcmp_0(a4, &GUID_NULL, 0x10u) )
    *a4 = *(struct _GUID *)(*((_QWORD *)this + 7) + 44LL);
  v23 = FwpmProviderContextGetByKey3(v14, a4, &p);
  v83 = v23;
  if ( v23 )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v23);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v119) = 0;
      LOWORD(v114) = 0;
      v24 = *((_QWORD *)this + 6);
      if ( v24 )
      {
        v25 = *(_QWORD *)(v24 + 112);
        if ( v25 )
        {
          if ( *(_QWORD *)(v25 + 16) )
            v12 = *(_DWORD *)(v25 + 16);
        }
      }
      ConvertPortNoToString(&v114, v12);
      FormatRRASErrorString(&v119, L"FwpmProviderContextGetByKey failed: %d", v83);
      goto LABEL_20;
    }
    goto LABEL_210;
  }
  if ( !*((_DWORD *)this + 16) )
  {
LABEL_58:
    v108 = *(_QWORD *)(*((_QWORD *)this + 6) + 8LL);
    v30 = *((_QWORD *)this + 5);
    v109 = ++*(_QWORD *)(v30 + 8);
    v31 = *((_QWORD *)this + 6);
    v32 = *(_QWORD *)(v31 + 112);
    if ( *(_DWORD *)(v32 + 1472) != 2 || (*(_BYTE *)(v32 + 3200) & 1) != 0 )
      v33 = 8;
    else
      v33 = 0;
    v110 |= v33;
    v36 = ConvertInterfaceIndexToLuid(*(_DWORD *)(v31 + 108), &InterfaceLuid);
    v83 = v36;
    if ( !v36 )
    {
      v105.Value = InterfaceLuid.Value;
      goto LABEL_94;
    }
    v37 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v36);
      v37 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (byte_1800AA941 & 4) == 0 )
    {
LABEL_95:
      if ( *(_BYTE *)(*((_QWORD *)this + 6) + 16LL) )
      {
        if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 1) != 0 && *((_BYTE *)v37 + 25) >= 5u )
          WPP_SF_(v37[2], 153, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
        if ( (byte_1800AA941 & 8) == 0 )
          goto LABEL_116;
        LOWORD(v114) = 0;
        v45 = *((_QWORD *)this + 6);
        if ( v45 && (v46 = *(_QWORD *)(v45 + 112)) != 0 && *(_QWORD *)(v46 + 16) )
          v47 = *(unsigned int *)(v46 + 16);
        else
          v47 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v114, v47);
        if ( (byte_1800AA941 & 8) == 0 )
          goto LABEL_116;
        v48 = *((_QWORD *)this + 6);
        v49 = (_QWORD *)(v48 + 112);
        if ( v48 )
        {
          if ( *v49 )
            v50 = *v49 + 2686LL;
          else
            v50 = 0;
          if ( *v49 )
          {
            v51 = (__int128 *)(*v49 + 2120LL);
LABEL_115:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceInfo,
              (unsigned int)L"TunnelProtocolV4",
              (_DWORD)v51,
              v50,
              (__int64)&v114);
LABEL_116:
            v96 = 0;
            v97 = ntohl(*(_DWORD *)(*((_QWORD *)this + 6) + 48LL));
            v100 = ntohl(*(_DWORD *)(*((_QWORD *)this + 6) + 68LL));
            v103 = 1;
            v52 = *((_QWORD *)p + 10);
            v106 = 0;
            v37 = (PVOID *)WPP_GLOBAL_Control;
LABEL_139:
            v104 = v52;
            if ( v10 != 2 && v11 != 2 )
            {
              v61 = *((_QWORD *)this + 7) + 28LL;
              v112 = v61;
              if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 1) != 0 && *((_BYTE *)v37 + 25) >= 6u )
              {
                WPP_SF__guid_(v37[2], 155, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v61);
                v37 = (PVOID *)WPP_GLOBAL_Control;
              }
            }
            if ( !a3 )
            {
LABEL_167:
              _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 6) + 204LL));
              StartIkeextService();
              v69 = IPsecSaInitiateAsync0(v86, &v96, v88, *((_QWORD *)this + 6));
              v83 = v69;
              if ( !v69 )
                goto LABEL_209;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  157,
                  &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
                  v69);
              }
              if ( (byte_1800AA941 & 4) == 0
                || ((LOWORD(v119) = 0, LOWORD(v114) = 0, (v70 = *((_QWORD *)this + 6)) == 0)
                 || (v71 = *(_QWORD *)(v70 + 112)) == 0
                 || !*(_QWORD *)(v71 + 16)
                  ? (v72 = 0xFFFFFFFFLL)
                  : (v72 = *(unsigned int *)(v71 + 16)),
                    ConvertPortNoToString(&v114, v72),
                    FormatRRASErrorString(&v119, L"IPsecSaInitiateAsync0 returned: %d", v83),
                    (byte_1800AA941 & 4) == 0) )
              {
LABEL_188:
                BaseConnection::DeleteRef(*((BaseConnection **)this + 6));
                if ( (unsigned __int8)IsIkeextServiceRunning() )
                  goto LABEL_209;
                v83 = 827;
                v15 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    158,
                    &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
                    827);
                  v15 = (PVOID *)WPP_GLOBAL_Control;
                }
                if ( (byte_1800AA941 & 4) == 0 )
                  goto LABEL_210;
                LOWORD(v114) = 0;
                v77 = *((_QWORD *)this + 6);
                if ( v77 )
                {
                  v78 = *(_QWORD *)(v77 + 112);
                  if ( v78 )
                  {
                    if ( *(_QWORD *)(v78 + 16) )
                      v12 = *(_DWORD *)(v78 + 16);
                  }
                }
                ConvertPortNoToString(&v114, v12);
                if ( (byte_1800AA941 & 4) == 0 )
                  goto LABEL_209;
                v79 = *((_QWORD *)this + 6);
                v80 = (_QWORD *)(v79 + 112);
                if ( v79 )
                {
                  if ( *v80 )
                    v20 = *v80 + 2686LL;
                  else
                    v20 = 0;
                  if ( *v80 )
                  {
                    v21 = (__int128 *)(*v80 + 2120LL);
LABEL_207:
                    v22 = L"IKEEXT Service is not running, hence return ERROR_IPSEC_SERVICE_STOPPED";
                    goto LABEL_208;
                  }
                }
                else
                {
                  v20 = 0;
                }
                v21 = &v113;
                goto LABEL_207;
              }
              v73 = *((_QWORD *)this + 6);
              v74 = (_QWORD *)(v73 + 112);
              if ( v73 )
              {
                if ( *v74 )
                  v75 = *v74 + 2686LL;
                else
                  v75 = 0;
                if ( *v74 )
                {
                  v76 = (__int128 *)(*v74 + 2120LL);
LABEL_187:
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasVpnIkeParamTraceError,
                    (unsigned int)&v119,
                    (_DWORD)v76,
                    v75,
                    (__int64)&v114);
                  goto LABEL_188;
                }
              }
              else
              {
                v75 = 0;
              }
              v76 = &v113;
              goto LABEL_187;
            }
            if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 1) != 0 && *((_BYTE *)v37 + 25) >= 5u )
              WPP_SF_(v37[2], 156, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
            if ( (byte_1800AA941 & 8) == 0
              || ((LOWORD(v114) = 0, (v62 = *((_QWORD *)this + 6)) == 0)
               || (v63 = *(_QWORD *)(v62 + 112)) == 0
               || !*(_QWORD *)(v63 + 16)
                ? (v64 = 0xFFFFFFFFLL)
                : (v64 = *(unsigned int *)(v63 + 16)),
                  ConvertPortNoToString(&v114, v64),
                  (byte_1800AA941 & 8) == 0) )
            {
LABEL_166:
              v110 |= 0x20u;
              v108 = *(_QWORD *)BaseConnection::GetReauthConnectionId(*((_QWORD *)this + 6), &v85);
              v111 = *(_QWORD *)(*((_QWORD *)this + 6) + 8LL);
              goto LABEL_167;
            }
            v65 = *((_QWORD *)this + 6);
            v66 = (_QWORD *)(v65 + 112);
            if ( v65 )
            {
              if ( *v66 )
                v67 = *v66 + 2686LL;
              else
                v67 = 0;
              if ( *v66 )
              {
                v68 = (__int128 *)(*v66 + 2120LL);
LABEL_165:
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasVpnIkeParamTraceInfo,
                  (unsigned int)L"NAP Reauth",
                  (_DWORD)v68,
                  v67,
                  (__int64)&v114);
                goto LABEL_166;
              }
            }
            else
            {
              v67 = 0;
            }
            v68 = &v113;
            goto LABEL_165;
          }
        }
        else
        {
          v50 = 0;
        }
        v51 = &v113;
        goto LABEL_115;
      }
      if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 1) != 0 && *((_BYTE *)v37 + 25) >= 5u )
      {
        WPP_SF_(v37[2], 154, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
        v37 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( (byte_1800AA941 & 8) == 0 )
      {
LABEL_138:
        v96 = 1;
        v60 = *((_QWORD *)this + 6);
        v97 = *(_DWORD *)(v60 + 52);
        v98 = *(_QWORD *)(v60 + 56);
        v99 = *(_DWORD *)(v60 + 64);
        v100 = *(_DWORD *)(v60 + 72);
        v101 = *(_QWORD *)(v60 + 76);
        v102 = *(_DWORD *)(v60 + 84);
        v103 = 1;
        v52 = *((_QWORD *)p + 10);
        v106 = 1;
        goto LABEL_139;
      }
      LOWORD(v114) = 0;
      v53 = *((_QWORD *)this + 6);
      if ( v53 && (v54 = *(_QWORD *)(v53 + 112)) != 0 && *(_QWORD *)(v54 + 16) )
        v55 = *(unsigned int *)(v54 + 16);
      else
        v55 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v114, v55);
      if ( (byte_1800AA941 & 8) == 0 )
      {
LABEL_137:
        v37 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_138;
      }
      v56 = *((_QWORD *)this + 6);
      v57 = (_QWORD *)(v56 + 112);
      if ( v56 )
      {
        if ( *v57 )
          v58 = *v57 + 2686LL;
        else
          v58 = 0;
        if ( *v57 )
        {
          v59 = (__int128 *)(*v57 + 2120LL);
LABEL_136:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"TunnelProtocolV6",
            (_DWORD)v59,
            v58,
            (__int64)&v114);
          goto LABEL_137;
        }
      }
      else
      {
        v58 = 0;
      }
      v59 = &v113;
      goto LABEL_136;
    }
    LOWORD(v119) = 0;
    LOWORD(v114) = 0;
    v38 = *((_QWORD *)this + 6);
    if ( v38 && (v39 = *(_QWORD *)(v38 + 112)) != 0 && *(_QWORD *)(v39 + 16) )
      v40 = *(unsigned int *)(v39 + 16);
    else
      v40 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v114, v40);
    FormatRRASErrorString(&v119, L"ConvertInterfaceIndexToLuid failed: %!WINERROR!", v83);
    if ( (byte_1800AA941 & 4) == 0 )
    {
LABEL_94:
      v37 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_95;
    }
    v41 = *((_QWORD *)this + 6);
    v42 = (_QWORD *)(v41 + 112);
    if ( v41 )
    {
      if ( *v42 )
        v43 = *v42 + 2686LL;
      else
        v43 = 0;
      if ( *v42 )
      {
        v44 = (__int128 *)(*v42 + 2120LL);
LABEL_92:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v119,
          (_DWORD)v44,
          v43,
          (__int64)&v114);
        goto LABEL_94;
      }
    }
    else
    {
      v43 = 0;
    }
    v44 = &v113;
    goto LABEL_92;
  }
  v26 = ClientBFEHandler::IsCertSubjectNameCheckDisabled(this, &v85);
  v83 = v26;
  v28 = v85;
  if ( !v26 )
    goto LABEL_49;
  v29 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_54;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v26);
    v26 = v83;
LABEL_49:
    v29 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 1) != 0 && *((_BYTE *)v29 + 25) >= 5u )
  {
    LOBYTE(v27) = v28 != 0;
    WPP_SF_c(v29[2], 150, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v27);
    v26 = v83;
  }
LABEL_54:
  if ( !v26 && v28 )
    goto LABEL_58;
  v85 = 258;
  v83 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _BYTE *, int *))&xmmword_1800AA970 + 1))(
          *(_QWORD *)(*((_QWORD *)this + 6) + 24LL),
          0,
          v118,
          &v85);
  if ( !v83 )
  {
    *(_QWORD *)&v95[0] = v118;
    v107 = v95;
    goto LABEL_58;
  }
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v83);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v119) = 0;
    LOWORD(v114) = 0;
    v34 = *((_QWORD *)this + 6);
    if ( v34 )
    {
      v35 = *(_QWORD *)(v34 + 112);
      if ( v35 )
      {
        if ( *(_QWORD *)(v35 + 16) )
          v12 = *(_DWORD *)(v35 + 16);
      }
    }
    ConvertPortNoToString(&v114, v12);
    FormatRRASErrorString(&v119, L"RasGetPortUserData failed: %d", v83);
    goto LABEL_20;
  }
LABEL_210:
  if ( p )
  {
    FwpmFreeMemory0(&p);
    p = 0;
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 6u )
    WPP_SF_d(v15[2], 159, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v83);
  v81 = v83;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v89);
  return v81;
}

```

## disassembly

```asm
0x180039278  mov     [rsp-8+arg_10], rbx
0x18003927d  push    rbp
0x18003927e  push    rsi
0x18003927f  push    rdi
0x180039280  push    r12
0x180039282  push    r13
0x180039284  push    r14
0x180039286  push    r15
0x180039288  lea     rbp, [rsp-9E0h]
0x180039290  sub     rsp, 0AE0h
0x180039297  mov     rax, cs:__security_cookie
0x18003929e  xor     rax, rsp
0x1800392a1  mov     [rbp+0A10h+var_40], rax
0x1800392a8  mov     rdi, r9
0x1800392ab  mov     r13b, r8b
0x1800392ae  mov     [rsp+0B10h+var_AA8], rdx
0x1800392b3  mov     rbx, rcx
0x1800392b6  xor     edx, edx; Val
0x1800392b8  mov     r8d, 0A0h; Size
0x1800392be  lea     rcx, [rbp+0A10h+var_A30]; void *
0x1800392c2  call    memset_0
0x1800392c7  xor     r14d, r14d
0x1800392ca  mov     [rsp+0B10h+var_AD0], r14d
0x1800392cf  mov     [rsp+0B10h+p], r14
0x1800392d4  xorps   xmm0, xmm0
0x1800392d7  movups  [rbp+0A10h+var_A68], xmm0
0x1800392db  movups  [rbp+0A10h+var_A58], xmm0
0x1800392df  movups  [rbp+0A10h+var_A48], xmm0
0x1800392e3  mov     [rsp+0B10h+var_AC0], r14d
0x1800392e8  xor     edx, edx; Val
0x1800392ea  mov     r8d, 102h; Size
0x1800392f0  lea     rcx, [rbp+0A10h+var_950]; void *
0x1800392f7  call    memset_0
0x1800392fc  mov     qword ptr [rsp+0B10h+InterfaceLuid], r14
0x180039301  mov     [rsp+0B10h+var_AB8], r14
0x180039306  mov     rax, [rbx+30h]
0x18003930a  mov     rcx, [rax+70h]
0x18003930e  mov     r15d, [rcx+5C0h]
0x180039315  mov     r12d, [rcx+28h]
0x180039319  lea     rax, WPP_GLOBAL_Control
0x180039320  mov     rcx, cs:WPP_GLOBAL_Control
0x180039327  cmp     rcx, rax
0x18003932a  jz      short loc_180039366
0x18003932c  test    byte ptr [rcx+1Ch], 1
0x180039330  jz      short loc_180039366
0x180039332  cmp     byte ptr [rcx+19h], 6
0x180039336  jb      short loc_180039366
0x180039338  cmp     r12d, 2
0x18003933c  setz    r8b
0x180039340  cmp     r15d, 2
0x180039344  setz    dl
0x180039347  test    r13b, r13b
0x18003934a  setnz   al
0x18003934d  mov     [rsp+0B10h+var_AE0], r8b
0x180039352  mov     byte ptr [rsp+0B10h+var_AE8], dl
0x180039356  mov     byte ptr [rsp+0B10h+var_AF0], al
0x18003935a  mov     r9, rdi
0x18003935d  mov     rcx, [rcx+10h]
0x180039361  call    WPP_SF__guid_ccc
0x180039366  mov     [rbp+0A10h+var_840], r14d
0x18003936d  xor     edx, edx; Val
0x18003936f  mov     r8d, 7FCh; Size
0x180039375  lea     rcx, [rbp+0A10h+var_83C]; void *
0x18003937c  call    memset_0
0x180039381  mov     [rbp+0A10h+var_980], r14d
0x180039388  xorps   xmm0, xmm0
0x18003938b  xor     eax, eax
0x18003938d  movups  [rbp+0A10h+var_97C], xmm0
0x180039394  movups  [rbp+0A10h+var_96C], xmm0
0x18003939b  mov     [rbp+0A10h+var_95C], eax
0x1800393a1  movups  [rbp+0A10h+var_990], xmm0
0x1800393a8  xorps   xmm1, xmm1
0x1800393ab  movdqu  [rsp+0B10h+var_A98], xmm1
0x1800393b1  mov     [rsp+0B10h+var_AA0], r14
0x1800393b6  movdqu  [rbp+0A10h+var_A88], xmm0
0x1800393bb  mov     [rbp+0A10h+var_A78], r14
0x1800393bf  or      esi, 0FFFFFFFFh
0x1800393c2  mov     [rbp+0A10h+var_A70], esi
0x1800393c5  mov     [rbp+0A10h+var_A6C], r14d
0x1800393c9  test    cs:byte_1800AA941, 8
0x1800393d0  jz      short loc_1800393F8
0x1800393d2  mov     rax, [rbx+30h]
0x1800393d6  mov     [rsp+0B10h+var_AF0], rax; void *
0x1800393db  lea     r9, ?RasVpnIkeTraceFunctionWithConnObj@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x1800393e2  lea     r8, [rsp+0B10h+var_AD0]; unsigned int *
0x1800393e7  lea     rdx, aClientbfehandl_4; "ClientBFEHandler::StartSANegotiation"
0x1800393ee  lea     rcx, [rsp+0B10h+var_AA0]; this
0x1800393f3  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x1800393f8  xor     edx, edx; Val
0x1800393fa  mov     r8d, 0A0h; Size
0x180039400  lea     rcx, [rbp+0A10h+var_A30]; void *
0x180039404  call    memset_0
0x180039409  lea     rcx, [rsp+0B10h+var_AB8]; void **
0x18003940e  call    ?GetBfeHandle@BFEHandler@@SAKPEAPEAX@Z; BFEHandler::GetBfeHandle(void * *)
0x180039413  mov     [rsp+0B10h+var_AD0], eax
0x180039417  mov     r14, [rsp+0B10h+var_AB8]
0x18003941c  test    r14, r14
0x18003941f  jnz     loc_180039524
0x180039425  lea     r14, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x18003942c  test    eax, eax
0x18003942e  jz      short loc_180039463
0x180039430  mov     rcx, cs:WPP_GLOBAL_Control
0x180039437  lea     rdx, WPP_GLOBAL_Control
0x18003943e  cmp     rcx, rdx
0x180039441  jz      short loc_18003946A
0x180039443  test    byte ptr [rcx+1Ch], 1
0x180039447  jz      short loc_18003946A
0x180039449  cmp     byte ptr [rcx+19h], 2
0x18003944d  jb      short loc_18003946A
0x18003944f  mov     edx, 93h
0x180039454  mov     r9d, eax
0x180039457  mov     r8, r14
0x18003945a  mov     rcx, [rcx+10h]
0x18003945e  call    WPP_SF_d
0x180039463  mov     rcx, cs:WPP_GLOBAL_Control
0x18003946a  mov     dil, 4
0x18003946d  test    cs:byte_1800AA941, dil
0x180039474  jz      loc_180039F14
0x18003947a  xor     eax, eax
0x18003947c  mov     word ptr [rbp+0A10h+var_840], ax
0x180039483  mov     word ptr [rbp+0A10h+var_980], ax
0x18003948a  mov     rax, [rbx+30h]
0x18003948e  test    rax, rax
0x180039491  jz      short loc_1800394A6
0x180039493  mov     rax, [rax+70h]
0x180039497  test    rax, rax
0x18003949a  jz      short loc_1800394A6
0x18003949c  cmp     qword ptr [rax+10h], 0
0x1800394a1  jz      short loc_1800394A6
0x1800394a3  mov     esi, [rax+10h]
0x1800394a6  mov     edx, esi
0x1800394a8  lea     rcx, [rbp+0A10h+var_980]
0x1800394af  call    ConvertPortNoToString
0x1800394b4  lea     rdx, aGetbfehandleFa; "GetBfeHandle failed: %d"
0x1800394bb  mov     r8d, [rsp+0B10h+var_AD0]
0x1800394c0  lea     rcx, [rbp+0A10h+var_840]
0x1800394c7  call    FormatRRASErrorString
0x1800394cc  test    cs:byte_1800AA941, dil
0x1800394d3  jz      loc_180039F0D
0x1800394d9  mov     rcx, [rbx+30h]
0x1800394dd  lea     rax, [rcx+70h]
0x1800394e1  test    rcx, rcx
0x1800394e4  jz      short loc_18003950F
0x1800394e6  mov     rdx, [rax]
0x1800394e9  test    rdx, rdx
0x1800394ec  jz      short loc_1800394F7
0x1800394ee  lea     rcx, [rdx+0A7Eh]
0x1800394f5  jmp     short loc_1800394FE
0x1800394f7  test    rcx, rcx
0x1800394fa  jz      short loc_18003950F
0x1800394fc  xor     ecx, ecx
0x1800394fe  mov     rdx, [rax]
0x180039501  test    rdx, rdx
0x180039504  jz      short loc_180039511
0x180039506  lea     r9, [rdx+848h]
0x18003950d  jmp     short loc_180039518
0x18003950f  xor     ecx, ecx
0x180039511  lea     r9, [rbp+0A10h+var_990]
0x180039518  lea     r8, [rbp+0A10h+var_840]
0x18003951f  jmp     loc_180039EE9
0x180039524  mov     r8d, 10h; Size
0x18003952a  lea     rdx, GUID_NULL; Buf2
0x180039531  mov     rcx, rdi; Buf1
0x180039534  call    memcmp_0
0x180039539  test    eax, eax
0x18003953b  jnz     short loc_180039549
0x18003953d  mov     rax, [rbx+38h]
0x180039541  movups  xmm0, xmmword ptr [rax+2Ch]
0x180039545  movdqu  xmmword ptr [rdi], xmm0
0x180039549  lea     r8, [rsp+0B10h+p]
0x18003954e  mov     rdx, rdi
0x180039551  mov     rcx, r14
0x180039554  call    cs:__imp_FwpmProviderContextGetByKey3
0x18003955a  mov     [rsp+0B10h+var_AD0], eax
0x18003955e  test    eax, eax
0x180039560  jz      loc_1800395FD
0x180039566  lea     r14, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x18003956d  mov     rcx, cs:WPP_GLOBAL_Control
0x180039574  lea     r15, WPP_GLOBAL_Control
0x18003957b  cmp     rcx, r15
0x18003957e  jz      short loc_1800395A7
0x180039580  test    byte ptr [rcx+1Ch], 1
0x180039584  jz      short loc_1800395A7
0x180039586  cmp     byte ptr [rcx+19h], 2
0x18003958a  jb      short loc_1800395A7
0x18003958c  mov     edx, 94h
0x180039591  mov     r9d, eax
0x180039594  mov     r8, r14
0x180039597  mov     rcx, [rcx+10h]
0x18003959b  call    WPP_SF_d
0x1800395a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800395a7  mov     dil, 4
0x1800395aa  test    cs:byte_1800AA941, dil
0x1800395b1  jz      loc_180039F14
0x1800395b7  xor     eax, eax
0x1800395b9  mov     word ptr [rbp+0A10h+var_840], ax
0x1800395c0  mov     word ptr [rbp+0A10h+var_980], ax
0x1800395c7  mov     rax, [rbx+30h]
0x1800395cb  test    rax, rax
0x1800395ce  jz      short loc_1800395E3
0x1800395d0  mov     rax, [rax+70h]
0x1800395d4  test    rax, rax
0x1800395d7  jz      short loc_1800395E3
0x1800395d9  cmp     qword ptr [rax+10h], 0
0x1800395de  jz      short loc_1800395E3
0x1800395e0  mov     esi, [rax+10h]
0x1800395e3  mov     edx, esi
0x1800395e5  lea     rcx, [rbp+0A10h+var_980]
0x1800395ec  call    ConvertPortNoToString
0x1800395f1  lea     rdx, aFwpmproviderco; "FwpmProviderContextGetByKey failed: %d"
0x1800395f8  jmp     loc_1800394BB
0x1800395fd  lea     r14, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180039604  cmp     dword ptr [rbx+40h], 0
0x180039608  jz      loc_1800396E5
0x18003960e  lea     rdx, [rsp+0B10h+var_AC0]; int *
0x180039613  mov     rcx, rbx; this
0x180039616  call    ?IsCertSubjectNameCheckDisabled@ClientBFEHandler@@IEAAKPEAH@Z; ClientBFEHandler::IsCertSubjectNameCheckDisabled(int *)
0x18003961b  mov     [rsp+0B10h+var_AD0], eax
0x18003961f  mov     edi, [rsp+0B10h+var_AC0]
0x180039623  test    eax, eax
0x180039625  jz      short loc_18003965E
0x180039627  mov     rcx, cs:WPP_GLOBAL_Control
0x18003962e  lea     rdx, WPP_GLOBAL_Control
0x180039635  cmp     rcx, rdx
0x180039638  jz      short loc_180039698
0x18003963a  test    byte ptr [rcx+1Ch], 1
0x18003963e  jz      short loc_18003966C
0x180039640  cmp     byte ptr [rcx+19h], 2
0x180039644  jb      short loc_18003966C
0x180039646  mov     edx, 95h
0x18003964b  mov     r9d, eax
0x18003964e  mov     r8, r14
0x180039651  mov     rcx, [rcx+10h]
0x180039655  call    WPP_SF_d
0x18003965a  mov     eax, [rsp+0B10h+var_AD0]
0x18003965e  lea     rdx, WPP_GLOBAL_Control
0x180039665  mov     rcx, cs:WPP_GLOBAL_Control
0x18003966c  cmp     rcx, rdx
0x18003966f  jz      short loc_180039698
0x180039671  test    byte ptr [rcx+1Ch], 1
0x180039675  jz      short loc_180039698
0x180039677  cmp     byte ptr [rcx+19h], 5
0x18003967b  jb      short loc_180039698
0x18003967d  test    edi, edi
0x18003967f  setnz   r9b
0x180039683  mov     edx, 96h
0x180039688  mov     r8, r14
0x18003968b  mov     rcx, [rcx+10h]
0x18003968f  call    WPP_SF_c
0x180039694  mov     eax, [rsp+0B10h+var_AD0]
0x180039698  test    eax, eax
0x18003969a  jnz     short loc_1800396A0
0x18003969c  test    edi, edi
0x18003969e  jnz     short loc_1800396E5
0x1800396a0  mov     [rsp+0B10h+var_AC0], 102h
0x1800396a8  mov     rcx, [rbx+30h]
0x1800396ac  lea     r9, [rsp+0B10h+var_AC0]
0x1800396b1  lea     r8, [rbp+0A10h+var_950]
0x1800396b8  xor     edx, edx
0x1800396ba  mov     rcx, [rcx+18h]
0x1800396be  mov     rax, qword ptr cs:xmmword_1800AA970+8
0x1800396c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396ca  mov     [rsp+0B10h+var_AD0], eax
0x1800396ce  test    eax, eax
0x1800396d0  jnz     short loc_18003972A
0x1800396d2  lea     rax, [rbp+0A10h+var_950]
0x1800396d9  mov     qword ptr [rbp+0A10h+var_A68], rax
0x1800396dd  lea     rax, [rbp+0A10h+var_A68]
0x1800396e1  mov     [rbp+0A10h+var_9D8], rax
0x1800396e5  mov     rax, [rbx+30h]
0x1800396e9  mov     rcx, [rax+8]
0x1800396ed  mov     [rbp+0A10h+var_9D0], rcx
0x1800396f1  mov     rax, [rbx+28h]
0x1800396f5  inc     qword ptr [rax+8]
0x1800396f9  mov     rax, [rax+8]
0x1800396fd  mov     [rbp+0A10h+var_9C8], rax
0x180039701  mov     rcx, [rbx+30h]
0x180039705  mov     rax, [rcx+70h]
0x180039709  cmp     dword ptr [rax+5C0h], 2
0x180039710  jnz     loc_1800397BC
0x180039716  test    byte ptr [rax+0C80h], 1
0x18003971d  jnz     loc_1800397BC
0x180039723  xor     eax, eax
0x180039725  jmp     loc_1800397C1
0x18003972a  mov     rcx, cs:WPP_GLOBAL_Control
0x180039731  lea     rax, WPP_GLOBAL_Control
0x180039738  cmp     rcx, rax
0x18003973b  jz      short loc_180039766
0x18003973d  test    byte ptr [rcx+1Ch], 1
0x180039741  jz      short loc_180039766
0x180039743  cmp     byte ptr [rcx+19h], 2
0x180039747  jb      short loc_180039766
0x180039749  mov     edx, 97h
0x18003974e  mov     r9d, [rsp+0B10h+var_AD0]
0x180039753  mov     r8, r14
0x180039756  mov     rcx, [rcx+10h]
0x18003975a  call    WPP_SF_d
0x18003975f  mov     rcx, cs:WPP_GLOBAL_Control
0x180039766  mov     dil, 4
0x180039769  test    cs:byte_1800AA941, dil
  ... truncated ...
```
