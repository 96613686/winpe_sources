# VPNIKEClientConnection::ProcessStart(_PROTOCOL_START &)

- ea: `0x18001bd20`
- end: `0x18001c964`
- name: `?ProcessStart@VPNIKEClientConnection@@UEAAXAEAU_PROTOCOL_START@@@Z`
- size: `3140`
- prototype: `void __fastcall(VPNIKEClientConnection *__hidden this, struct _PROTOCOL_START *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007610`
- `0x180007794`
- `0x180009824`
- `0x180013450`
- `0x18001a76c`
- `0x18001bd20`
- `0x18001f10c`
- `0x180031788`
- `0x180032690`
- `0x1800389e4`
- `0x180039278`
- `0x1800466a4`
- `0x18005ad28`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c2ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c458`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c2ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c458`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c2dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c446`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c2dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c446`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c8ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c8c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c8ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c8c3`

## string_xrefs

- `0x18001bebb`: `User already cancelled this connection. Hence exiting.`
- `0x18001c7ce`: `RasProtocolStarted failed: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VPNIKEClientConnection::ProcessStart(VPNIKEClientConnection *this, struct _PROTOCOL_START *a2)
{
  unsigned int v4; // esi
  char v5; // dl
  __int64 v6; // rax
  __int64 v7; // rdx
  __int128 *v8; // r9
  char v9; // dl
  __int64 v10; // rcx
  int AuthenticationType; // r15d
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int128 *v14; // r9
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int128 *v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int128 *v21; // r9
  __int64 v22; // rax
  __int64 v23; // rdx
  __int128 *v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int128 *v27; // r9
  struct in_addr *v28; // r15
  struct in6_addr *v29; // r13
  __int64 v30; // rax
  HANDLE ProcessHeap; // rax
  _DWORD *v32; // rax
  _DWORD *v33; // r14
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int128 *v38; // r9
  unsigned int v39; // r14d
  __int64 v40; // rcx
  __int64 v41; // rdx
  HANDLE v42; // rax
  _OWORD *v43; // rax
  _OWORD *v44; // r14
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int128 *v48; // r9
  unsigned int v49; // r14d
  __int64 v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // rdx
  __int128 *v53; // r9
  __int64 v54; // rax
  unsigned int v55; // r15d
  unsigned int i; // r14d
  __int64 v57; // rax
  __int64 v58; // rdx
  __int128 *v59; // r9
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rdx
  struct _PROTOCOL_START *v63; // rdi
  unsigned int started; // [rsp+40h] [rbp-C0h] BYREF
  int v65; // [rsp+44h] [rbp-BCh]
  struct _GUID v66; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD *v67; // [rsp+60h] [rbp-A0h]
  int v68; // [rsp+70h] [rbp-90h]
  struct _PROTOCOL_START *v69; // [rsp+78h] [rbp-88h]
  __int64 v70; // [rsp+80h] [rbp-80h] BYREF
  __int128 v71; // [rsp+88h] [rbp-78h]
  __int128 v72; // [rsp+98h] [rbp-68h]
  __int64 v73; // [rsp+A8h] [rbp-58h]
  int v74; // [rsp+B0h] [rbp-50h]
  int v75; // [rsp+B4h] [rbp-4Ch]
  __int128 v76; // [rsp+B8h] [rbp-48h] BYREF
  struct _GUID v77; // [rsp+D0h] [rbp-30h] BYREF
  int v78; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v79; // [rsp+E4h] [rbp-1Ch]
  __int128 v80; // [rsp+F4h] [rbp-Ch]
  int v81; // [rsp+104h] [rbp+4h]
  int v82; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v83[2044]; // [rsp+114h] [rbp+14h] BYREF

  v69 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
  }
  started = 0;
  v66 = 0;
  v67 = 0;
  v77 = GUID_NULL;
  *((_DWORD *)this + 92) = 0;
  v82 = 0;
  memset_0(v83, 0, sizeof(v83));
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v76 = 0;
  v71 = 0;
  v70 = 0;
  v72 = 0;
  v73 = 0;
  v4 = -1;
  v74 = -1;
  v75 = 0;
  v5 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v70,
      L"VPNIKEClientConnection::ProcessStart",
      &started,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      *((void **)this + 14));
    v5 = byte_1800AA941;
  }
  if ( (*((_DWORD *)this + 38) & 0x8000) != 0 )
  {
    if ( (v5 & 4) != 0 )
    {
      LOWORD(v78) = 0;
      v6 = *((_QWORD *)this + 14);
      if ( v6 && *(_QWORD *)(v6 + 16) )
        v4 = *(_DWORD *)(v6 + 16);
      ConvertPortNoToString(&v78, v4);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v7 = *((_QWORD *)this + 14);
        LODWORD(v8) = v7 + 2120;
        if ( !v7 )
          v8 = &v76;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"User already cancelled this connection. Hence exiting.",
          (_DWORD)v8,
          (v7 + 2686) & -(__int64)(v7 != 0),
          (__int64)&v78);
      }
    }
    goto LABEL_160;
  }
  AuthenticationType = ConnectionParams::GetAuthenticationType(*((_QWORD *)this + 14));
  v68 = AuthenticationType;
  if ( AuthenticationType == 1 )
  {
    if ( *((_QWORD *)this + 15) )
    {
      if ( (v9 & 4) != 0 )
      {
        LOWORD(v82) = 0;
        LOWORD(v78) = 0;
        if ( v10 && *(_QWORD *)(v10 + 16) )
          v12 = *(unsigned int *)(v10 + 16);
        else
          v12 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v78, v12);
        FormatRRASErrorString(&v82, L"===> Eap Method Type : %d", *((unsigned int *)a2 + 1721));
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v13 = *((_QWORD *)this + 14);
          LODWORD(v14) = v13 + 2120;
          if ( !v13 )
            v14 = &v76;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v82,
            (_DWORD)v14,
            (v13 + 2686) & -(__int64)(v13 != 0),
            (__int64)&v78);
        }
      }
      started = ClientEAPAuthHandler::SetEapAuthData(
                  *((ClientEAPAuthHandler **)this + 15),
                  (STRSAFE_LPCSTR)v69 + 1942,
                  (char *)v69 + 2456,
                  *((_DWORD *)v69 + 1721),
                  *((struct _RAS_CUSTOM_AUTH_DATA **)v69 + 861),
                  *((struct _RAS_CUSTOM_AUTH_DATA **)v69 + 862),
                  *(struct _LUID *)((char *)v69 + 2472));
      if ( started )
      {
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_160;
        LOWORD(v82) = 0;
        LOWORD(v78) = 0;
        v15 = *((_QWORD *)this + 14);
        if ( v15 && *(_QWORD *)(v15 + 16) )
          v4 = *(_DWORD *)(v15 + 16);
        ConvertPortNoToString(&v78, v4);
        FormatRRASErrorString(&v82, L"SetEapAuthData failed: %d", started);
LABEL_33:
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_160;
        v16 = *((_QWORD *)this + 14);
        v17 = (v16 + 2686) & -(__int64)(v16 != 0);
        LODWORD(v18) = v16 + 2120;
        if ( !v16 )
          v18 = &v76;
LABEL_159:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v82,
          (_DWORD)v18,
          v17,
          (__int64)&v78);
        goto LABEL_160;
      }
      goto LABEL_69;
    }
LABEL_57:
    if ( (v9 & 8) != 0 )
    {
      LOWORD(v78) = 0;
      if ( v10 && *(_QWORD *)(v10 + 16) )
        v25 = *(unsigned int *)(v10 + 16);
      else
        v25 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v78, v25);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v26 = *((_QWORD *)this + 14);
        LODWORD(v27) = v26 + 2120;
        if ( !v26 )
          v27 = &v76;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"===> Setting EAP Auth Type NONE",
          (_DWORD)v27,
          (v26 + 2686) & -(__int64)(v26 != 0),
          (__int64)&v78);
      }
    }
    if ( AuthenticationType == 3 )
    {
      v65 = 0;
      if ( *(_DWORD *)(*((_QWORD *)this + 14) + 1472LL) == 2 )
      {
        v28 = (struct in_addr *)((char *)this + 68);
        v29 = (struct in6_addr *)((char *)this + 72);
        goto LABEL_76;
      }
    }
LABEL_69:
    v29 = (struct in6_addr *)((char *)this + 72);
    v28 = (struct in_addr *)((char *)this + 68);
    started = ClientBFEHandler::PlumbPolicy(
                *((ClientBFEHandler **)this + 26),
                *((_BYTE *)this + 16),
                (struct in_addr *)this + 17,
                (struct in6_addr *)((char *)this + 72),
                (unsigned __int8 *)(*((_QWORD *)this + 14) + 914LL),
                *(_DWORD *)(*((_QWORD *)this + 14) + 1172LL));
    if ( started )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_160;
      LOWORD(v82) = 0;
      LOWORD(v78) = 0;
      v30 = *((_QWORD *)this + 14);
      if ( v30 && *(_QWORD *)(v30 + 16) )
        v4 = *(_DWORD *)(v30 + 16);
      ConvertPortNoToString(&v78, v4);
      FormatRRASErrorString(&v82, L"PlumbPolicy failed: %d", started);
      goto LABEL_33;
    }
    v65 = 1;
LABEL_76:
    if ( *((_BYTE *)this + 16) )
    {
      ProcessHeap = GetProcessHeap();
      v32 = HeapAlloc(ProcessHeap, 8u, 4u);
      v33 = v32;
      if ( !v32 )
      {
LABEL_78:
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_160;
        LOWORD(v82) = 0;
        LOWORD(v78) = 0;
        v34 = *((_QWORD *)this + 14);
        if ( v34 && *(_QWORD *)(v34 + 16) )
          v4 = *(_DWORD *)(v34 + 16);
        ConvertPortNoToString(&v78, v4);
        FormatRRASErrorString(&v82, L"VPNIKE_MALLOC returned: %d", 8);
LABEL_156:
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_160;
        v62 = *((_QWORD *)this + 14);
        v17 = (v62 + 2686) & -(__int64)(v62 != 0);
        LODWORD(v18) = v62 + 2120;
        if ( !v62 )
          v18 = &v76;
        goto LABEL_159;
      }
      *(_QWORD *)v66.Data4 = v32;
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v78) = 0;
        v35 = *((_QWORD *)this + 14);
        if ( v35 && *(_QWORD *)(v35 + 16) )
          v36 = *(unsigned int *)(v35 + 16);
        else
          v36 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v78, v36);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v37 = *((_QWORD *)this + 14);
          LODWORD(v38) = v37 + 2120;
          if ( !v37 )
            v38 = &v76;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"Adding header v4 remote address to additional addresses",
            (_DWORD)v38,
            (v37 + 2686) & -(__int64)(v37 != 0),
            (__int64)&v78);
        }
      }
      *v33 = *((_DWORD *)this + 17);
      v66.Data1 = 1;
      v39 = (*((__int64 (__fastcall **)(_QWORD, __int64, _DWORD *, __int64))&xmmword_1800AA980 + 1))(
              *(_QWORD *)(*((_QWORD *)this + 14) + 24LL),
              2,
              v33,
              4);
      if ( v39 && (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v82) = 0;
        LOWORD(v78) = 0;
        v40 = *((_QWORD *)this + 14);
        if ( v40 && *(_QWORD *)(v40 + 16) )
          v41 = *(unsigned int *)(v40 + 16);
        else
          v41 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v78, v41);
        FormatRRASErrorString(&v82, L"RasSetConnectionUserData failed for v4: %d", v39);
        goto LABEL_116;
      }
    }
    else
    {
      v42 = GetProcessHeap();
      v43 = HeapAlloc(v42, 8u, 0x10u);
      v44 = v43;
      if ( !v43 )
        goto LABEL_78;
      v67 = v43;
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v78) = 0;
        v45 = *((_QWORD *)this + 14);
        if ( v45 && *(_QWORD *)(v45 + 16) )
          v46 = *(unsigned int *)(v45 + 16);
        else
          v46 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v78, v46);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v47 = *((_QWORD *)this + 14);
          LODWORD(v48) = v47 + 2120;
          if ( !v47 )
            v48 = &v76;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"Adding header v6 remote address to additional addresses",
            (_DWORD)v48,
            (v47 + 2686) & -(__int64)(v47 != 0),
            (__int64)&v78);
        }
      }
      *v44 = *(_OWORD *)((char *)this + 72);
      *(_DWORD *)&v66.Data2 = 1;
      v49 = (*((__int64 (__fastcall **)(_QWORD, __int64, _OWORD *))&xmmword_1800AA980 + 1))(
              *(_QWORD *)(*((_QWORD *)this + 14) + 24LL),
              3,
              v44);
      if ( v49 && (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v82) = 0;
        LOWORD(v78) = 0;
        v50 = *((_QWORD *)this + 14);
        if ( v50 && *(_QWORD *)(v50 + 16) )
          v51 = *(unsigned int *)(v50 + 16);
        else
          v51 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v78, v51);
        FormatRRASErrorString(&v82, L"RasSetConnectionUserData failed for v6: %d", v49);
LABEL_116:
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v52 = *((_QWORD *)this + 14);
          LODWORD(v53) = v52 + 2120;
          if ( !v52 )
            v53 = &v76;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v82,
            (_DWORD)v53,
            (v52 + 2686) & -(__int64)(*((_QWORD *)this + 14) != 0),
            (__int64)&v78);
        }
      }
    }
    LogAdditionalAddresses(&v66);
    VPNIKEConnection::UpdatePeerAdditionalAddresses(this, (struct _ADDITIONAL_ADDRESSES_ *)&v66);
    if ( v68 == 3
      && *(_DWORD *)(*((_QWORD *)this + 14) + 1472LL) == 2
      && (started = ClientBFEHandler::QueryPolicyID(
                      *((ClientBFEHandler **)this + 26),
                      *((_BYTE *)this + 16),
                      v28,
                      v29,
                      &v77)) != 0 )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_160;
      LOWORD(v82) = 0;
      LOWORD(v78) = 0;
      v54 = *((_QWORD *)this + 14);
      if ( v54 && *(_QWORD *)(v54 + 16) )
        v4 = *(_DWORD *)(v54 + 16);
      ConvertPortNoToString(&v78, v4);
      FormatRRASErrorString(&v82, L"QueryPolicyID failed: %d", started);
    }
    else
    {
      v55 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 26) + 40LL) + 24LL);
      for ( i = 0; i < v55; ++i )
      {
        _InterlockedIncrement((volatile signed __int32 *)this + 92);
        v66 = v77;
        started = ClientBFEHandler::StartSANegotiation(
                    *((ClientBFEHandler **)this + 26),
                    (void (*)(void *, const struct IPSEC_NEGOTIATION_STATUS0_ *))VPNIKEClientConnection::InitiateIkeCompleteCallback,
                    0,
                    &v66);
        if ( started )
        {
          if ( (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v82) = 0;
            LOWORD(v78) = 0;
            v57 = *((_QWORD *)this + 14);
            if ( v57 && *(_QWORD *)(v57 + 16) )
              v4 = *(_DWORD *)(v57 + 16);
            ConvertPortNoToString(&v78, v4);
            FormatRRASErrorString(&v82, L"StartSANegotiation failed: %d", started);
            if ( (byte_1800AA941 & 4) != 0 )
            {
              v58 = *((_QWORD *)this + 14);
              LODWORD(v59) = v58 + 2120;
              if ( !v58 )
                v59 = &v76;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceError,
                (unsigned int)&v82,
                (_DWORD)v59,
                (v58 + 2686) & -(__int64)(v58 != 0),
                (__int64)&v78);
            }
          }
          if ( v65 )
            ClientBFEHandler::DeletePolicy(*((void ***)this + 26));
          *((_DWORD *)this + 91) = started;
          _InterlockedDecrement((volatile signed __int32 *)this + 92);
          goto LABEL_160;
        }
      }
      VPNIKEClientConnection::UpdateConnectionState(this, 1u);
      started = ((__int64 (__fastcall *)(_QWORD))xmmword_1800AA990)(*((_QWORD *)this + 3));
      if ( started )
      {
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_160;
        LOWORD(v82) = 0;
        LOWORD(v78) = 0;
        v60 = *((_QWORD *)this + 14);
        if ( v60 && *(_QWORD *)(v60 + 16) )
          v4 = *(_DWORD *)(v60 + 16);
        ConvertPortNoToString(&v78, v4);
        FormatRRASErrorString(&v82, L"RasProtocolStarted failed: %d", started);
      }
      else
      {
        started = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))xmmword_1800AA980)(
                    0,
                    *(_QWORD *)(*((_QWORD *)this + 14) + 16LL),
                    *((_QWORD *)this + 14) + 32LL);
        if ( !started || (byte_1800AA941 & 4) == 0 )
          goto LABEL_160;
        LOWORD(v82) = 0;
        LOWORD(v78) = 0;
        v61 = *((_QWORD *)this + 14);
        if ( v61 && *(_QWORD *)(v61 + 16) )
          v4 = *(_DWORD *)(v61 + 16);
        ConvertPortNoToString(&v78, v4);
        FormatRRASErrorString(&v82, L"RasPortGetBundle failed: %d", started);
      }
    }
    goto LABEL_156;
  }
  if ( AuthenticationType != 3 || *(_DWORD *)(v10 + 1172) )
    goto LABEL_57;
  if ( (v9 & 8) != 0 )
  {
    LOWORD(v78) = 0;
    if ( v10 && *(_QWORD *)(v10 + 16) )
      v19 = *(unsigned int *)(v10 + 16);
    else
      v19 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v78, v19);
    v9 = byte_1800AA941;
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v20 = *((_QWORD *)this + 14);
      LODWORD(v21) = v20 + 2120;
      if ( !v20 )
        v21 = &v76;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceInfo,
        (unsigned int)L"===> Setting PSK Auth Type",
        (_DWORD)v21,
        (v20 + 2686) & -(__int64)(v20 != 0),
        (__int64)&v78);
      v9 = byte_1800AA941;
    }
  }
  if ( (v9 & 4) != 0 )
  {
    LOWORD(v78) = 0;
    v22 = *((_QWORD *)this + 14);
    if ( v22 && *(_QWORD *)(v22 + 16) )
      v4 = *(_DWORD *)(v22 + 16);
    ConvertPortNoToString(&v78, v4);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v23 = *((_QWORD *)this + 14);
      LODWORD(v24) = v23 + 2120;
      if ( !v23 )
        v24 = &v76;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceError,
        (unsigned int)L"Pre-shared key is not specified or empty",
        (_DWORD)v24,
        (v23 + 2686) & -(__int64)(v23 != 0),
        (__int64)&v78);
    }
  }
  started = 87;
LABEL_160:
  v63 = v69;
  LocalFree(*((HLOCAL *)v69 + 861));
  *((_QWORD *)v63 + 861) = 0;
  LocalFree(*((HLOCAL *)v63 + 862));
  *((_QWORD *)v63 + 862) = 0;
  if ( started )
  {
    v66 = 0;
    v67 = 0;
    VPNIKEConnection::UpdatePeerAdditionalAddresses(this, (struct _ADDITIONAL_ADDRESSES_ *)&v66);
    VPNIKEClientConnection::NotifyError(this, started);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v70);
}

```

## disassembly

```asm
0x18001bd20  mov     [rsp-8+arg_10], rbx
0x18001bd25  push    rbp
0x18001bd26  push    rsi
0x18001bd27  push    rdi
0x18001bd28  push    r12
0x18001bd2a  push    r13
0x18001bd2c  push    r14
0x18001bd2e  push    r15
0x18001bd30  lea     rbp, [rsp-820h]
0x18001bd38  sub     rsp, 920h
0x18001bd3f  mov     rax, cs:__security_cookie
0x18001bd46  xor     rax, rsp
0x18001bd49  mov     [rbp+850h+var_40], rax
0x18001bd50  mov     r13, rdx
0x18001bd53  mov     [rsp+950h+var_8D8], rdx
0x18001bd58  mov     rbx, rcx
0x18001bd5b  lea     r14, WPP_GLOBAL_Control
0x18001bd62  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd69  cmp     rcx, r14
0x18001bd6c  jz      short loc_18001BD8F
0x18001bd6e  test    byte ptr [rcx+1Ch], 1
0x18001bd72  jz      short loc_18001BD8F
0x18001bd74  cmp     byte ptr [rcx+19h], 6
0x18001bd78  jb      short loc_18001BD8F
0x18001bd7a  mov     edx, 26h ; '&'
0x18001bd7f  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001bd86  mov     rcx, [rcx+10h]
0x18001bd8a  call    WPP_SF_
0x18001bd8f  mov     [rsp+950h+var_910], 0
0x18001bd97  xorps   xmm0, xmm0
0x18001bd9a  xor     eax, eax
0x18001bd9c  movups  xmmword ptr [rsp+950h+var_900.Data1], xmm0
0x18001bda1  mov     [rsp+950h+var_8F0], rax
0x18001bda6  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18001bdad  movdqu  xmmword ptr [rbp+850h+var_880.Data1], xmm1
0x18001bdb2  mov     [rbx+170h], eax
0x18001bdb8  mov     [rbp+850h+var_840], eax
0x18001bdbb  xor     edx, edx; Val
0x18001bdbd  mov     r8d, 7FCh; Size
0x18001bdc3  lea     rcx, [rbp+850h+var_83C]; void *
0x18001bdc7  call    memset_0
0x18001bdcc  xor     eax, eax
0x18001bdce  mov     [rbp+850h+var_870], eax
0x18001bdd1  xorps   xmm0, xmm0
0x18001bdd4  movups  [rbp+850h+var_86C], xmm0
0x18001bdd8  movups  [rbp+850h+var_85C], xmm0
0x18001bddc  mov     [rbp+850h+var_84C], eax
0x18001bddf  movups  [rbp+850h+var_898], xmm0
0x18001bde3  xorps   xmm1, xmm1
0x18001bde6  movdqu  [rbp+850h+var_8C8], xmm1
0x18001bdeb  mov     [rbp+850h+var_8D0], rax
0x18001bdef  movdqu  [rbp+850h+var_8B8], xmm0
0x18001bdf4  mov     [rbp+850h+var_8A8], rax
0x18001bdf8  or      esi, 0FFFFFFFFh
0x18001bdfb  mov     [rbp+850h+var_8A0], esi
0x18001bdfe  mov     [rbp+850h+var_89C], eax
0x18001be01  mov     dl, cs:byte_1800AA941
0x18001be07  test    dl, 8
0x18001be0a  jz      short loc_18001BE37
0x18001be0c  mov     rax, [rbx+70h]
0x18001be10  mov     [rsp+950h+var_930], rax; void *
0x18001be15  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18001be1c  lea     r8, [rsp+950h+var_910]; unsigned int *
0x18001be21  lea     rdx, aVpnikeclientco_4; "VPNIKEClientConnection::ProcessStart"
0x18001be28  lea     rcx, [rbp+850h+var_8D0]; this
0x18001be2c  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18001be31  mov     dl, cs:byte_1800AA941
0x18001be37  test    dword ptr [rbx+98h], 8000h
0x18001be41  jz      loc_18001BEDA
0x18001be47  mov     edi, 4
0x18001be4c  test    dil, dl
0x18001be4f  jz      loc_18001C89F
0x18001be55  xor     eax, eax
0x18001be57  mov     word ptr [rbp+850h+var_870], ax
0x18001be5b  mov     rax, [rbx+70h]
0x18001be5f  test    rax, rax
0x18001be62  jz      short loc_18001BE6E
0x18001be64  cmp     qword ptr [rax+10h], 0
0x18001be69  jz      short loc_18001BE6E
0x18001be6b  mov     esi, [rax+10h]
0x18001be6e  mov     edx, esi
0x18001be70  lea     rcx, [rbp+850h+var_870]
0x18001be74  call    ConvertPortNoToString
0x18001be79  test    cs:byte_1800AA941, dil
0x18001be80  jz      loc_18001C89F
0x18001be86  mov     rdx, [rbx+70h]
0x18001be8a  mov     rax, rdx
0x18001be8d  lea     rcx, [rdx+0A7Eh]
0x18001be94  neg     rax
0x18001be97  sbb     r8, r8
0x18001be9a  and     r8, rcx
0x18001be9d  test    rdx, rdx
0x18001bea0  lea     r9, [rdx+848h]
0x18001bea7  jnz     short loc_18001BEAD
0x18001bea9  lea     r9, [rbp+850h+var_898]
0x18001bead  lea     rax, [rbp+850h+var_870]
0x18001beb1  mov     [rsp+950h+var_928], rax
0x18001beb6  mov     [rsp+950h+var_930], r8
0x18001bebb  lea     r8, aUserAlreadyCan; "User already cancelled this connection."...
0x18001bec2  lea     rdx, RasVpnIkeParamTraceError
0x18001bec9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001bed0  call    McTemplateU0zjzz_EventWriteTransfer
0x18001bed5  jmp     loc_18001C89F
0x18001beda  mov     rcx, [rbx+70h]
0x18001bede  call    ?GetAuthenticationType@ConnectionParams@@QEAA?AW4_IKEv2_AUTH_TYPE_@@XZ; ConnectionParams::GetAuthenticationType(void)
0x18001bee3  mov     r15d, eax
0x18001bee6  mov     [rsp+950h+var_8E0], eax
0x18001beea  mov     edi, 4
0x18001beef  lea     r14, RasVpnIkeParamTraceError
0x18001bef6  cmp     eax, 1
0x18001bef9  jnz     loc_18001C07C
0x18001beff  cmp     qword ptr [rbx+78h], 0
0x18001bf04  jz      loc_18001C1A2
0x18001bf0a  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001bf11  test    dil, dl
0x18001bf14  jz      loc_18001BFA3
0x18001bf1a  xor     eax, eax
0x18001bf1c  mov     word ptr [rbp+850h+var_840], ax
0x18001bf20  mov     word ptr [rbp+850h+var_870], ax
0x18001bf24  test    rcx, rcx
0x18001bf27  jz      short loc_18001BF34
0x18001bf29  cmp     [rcx+10h], rax
0x18001bf2d  jz      short loc_18001BF34
0x18001bf2f  mov     edx, [rcx+10h]
0x18001bf32  jmp     short loc_18001BF36
0x18001bf34  mov     edx, esi
0x18001bf36  lea     rcx, [rbp+850h+var_870]
0x18001bf3a  call    ConvertPortNoToString
0x18001bf3f  mov     r8d, [r13+1AE4h]
0x18001bf46  lea     rdx, aEapMethodTypeD; "===> Eap Method Type : %d"
0x18001bf4d  lea     rcx, [rbp+850h+var_840]
0x18001bf51  call    FormatRRASErrorString
0x18001bf56  test    cs:byte_1800AA941, dil
0x18001bf5d  jz      short loc_18001BFA3
0x18001bf5f  mov     rdx, [rbx+70h]
0x18001bf63  mov     rax, rdx
0x18001bf66  lea     rcx, [rdx+0A7Eh]
0x18001bf6d  neg     rax
0x18001bf70  sbb     r8, r8
0x18001bf73  and     r8, rcx
0x18001bf76  test    rdx, rdx
0x18001bf79  lea     r9, [rdx+848h]
0x18001bf80  jnz     short loc_18001BF86
0x18001bf82  lea     r9, [rbp+850h+var_898]
0x18001bf86  lea     rax, [rbp+850h+var_870]
0x18001bf8a  mov     [rsp+950h+var_928], rax
0x18001bf8f  mov     [rsp+950h+var_930], r8
0x18001bf94  lea     r8, [rbp+850h+var_840]
0x18001bf98  mov     rdx, r14
0x18001bf9b  mov     rcx, r12
0x18001bf9e  call    McTemplateU0zjzz_EventWriteTransfer
0x18001bfa3  mov     rcx, [rsp+950h+var_8D8]
0x18001bfa8  lea     r8, [rcx+998h]; char *
0x18001bfaf  lea     rdx, [rcx+796h]; pszSrc
0x18001bfb6  mov     rax, [rcx+9A8h]
0x18001bfbd  mov     qword ptr [rsp+950h+var_920.LowPart], rax; struct _LUID
0x18001bfc2  mov     rax, [rcx+1AF0h]
0x18001bfc9  mov     [rsp+950h+var_928], rax; struct _RAS_CUSTOM_AUTH_DATA *
0x18001bfce  mov     rax, [rcx+1AE8h]
0x18001bfd5  mov     [rsp+950h+var_930], rax; struct _RAS_CUSTOM_AUTH_DATA *
0x18001bfda  mov     r9d, [rcx+1AE4h]; unsigned int
0x18001bfe1  mov     rcx, [rbx+78h]; this
0x18001bfe5  call    ?SetEapAuthData@ClientEAPAuthHandler@@QEAAKPEAD0KPEAU_RAS_CUSTOM_AUTH_DATA@@1U_LUID@@@Z; ClientEAPAuthHandler::SetEapAuthData(char *,char *,ulong,_RAS_CUSTOM_AUTH_DATA *,_RAS_CUSTOM_AUTH_DATA *,_LUID)
0x18001bfea  mov     [rsp+950h+var_910], eax
0x18001bfee  test    eax, eax
0x18001bff0  jz      loc_18001C24B
0x18001bff6  test    cs:byte_1800AA941, dil
0x18001bffd  jz      loc_18001C898
0x18001c003  xor     eax, eax
0x18001c005  mov     word ptr [rbp+850h+var_840], ax
0x18001c009  mov     word ptr [rbp+850h+var_870], ax
0x18001c00d  mov     rax, [rbx+70h]
0x18001c011  test    rax, rax
0x18001c014  jz      short loc_18001C020
0x18001c016  cmp     qword ptr [rax+10h], 0
0x18001c01b  jz      short loc_18001C020
0x18001c01d  mov     esi, [rax+10h]
0x18001c020  mov     edx, esi
0x18001c022  lea     rcx, [rbp+850h+var_870]
0x18001c026  call    ConvertPortNoToString
0x18001c02b  lea     rdx, aSeteapauthdata; "SetEapAuthData failed: %d"
0x18001c032  mov     r8d, [rsp+950h+var_910]
0x18001c037  lea     rcx, [rbp+850h+var_840]
0x18001c03b  call    FormatRRASErrorString
0x18001c040  test    cs:byte_1800AA941, dil
0x18001c047  jz      loc_18001C898
0x18001c04d  mov     rdx, [rbx+70h]
0x18001c051  mov     rax, rdx
0x18001c054  neg     rax
0x18001c057  lea     rcx, [rdx+0A7Eh]
0x18001c05e  sbb     r8, r8
0x18001c061  and     r8, rcx
0x18001c064  lea     r9, [rdx+848h]
0x18001c06b  test    rdx, rdx
0x18001c06e  jnz     short loc_18001C074
0x18001c070  lea     r9, [rbp+850h+var_898]
0x18001c074  mov     rdx, r14
0x18001c077  jmp     loc_18001C87E
0x18001c07c  cmp     r15d, 3
0x18001c080  jnz     loc_18001C1A2
0x18001c086  cmp     dword ptr [rcx+494h], 0
0x18001c08d  jnz     loc_18001C1A2
0x18001c093  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001c09a  test    dl, 8
0x18001c09d  jz      short loc_18001C11C
0x18001c09f  xor     eax, eax
0x18001c0a1  mov     word ptr [rbp+850h+var_870], ax
0x18001c0a5  test    rcx, rcx
0x18001c0a8  jz      short loc_18001C0B5
0x18001c0aa  cmp     [rcx+10h], rax
0x18001c0ae  jz      short loc_18001C0B5
0x18001c0b0  mov     edx, [rcx+10h]
0x18001c0b3  jmp     short loc_18001C0B7
0x18001c0b5  mov     edx, esi
0x18001c0b7  lea     rcx, [rbp+850h+var_870]
0x18001c0bb  call    ConvertPortNoToString
0x18001c0c0  mov     dl, cs:byte_1800AA941
0x18001c0c6  test    dl, 8
0x18001c0c9  jz      short loc_18001C11C
0x18001c0cb  mov     rdx, [rbx+70h]
0x18001c0cf  mov     rax, rdx
0x18001c0d2  lea     rcx, [rdx+0A7Eh]
0x18001c0d9  neg     rax
0x18001c0dc  sbb     r8, r8
0x18001c0df  and     r8, rcx
0x18001c0e2  test    rdx, rdx
0x18001c0e5  lea     r9, [rdx+848h]
0x18001c0ec  jnz     short loc_18001C0F2
0x18001c0ee  lea     r9, [rbp+850h+var_898]
0x18001c0f2  lea     rax, [rbp+850h+var_870]
0x18001c0f6  mov     [rsp+950h+var_928], rax
0x18001c0fb  mov     [rsp+950h+var_930], r8
0x18001c100  lea     r8, aSettingPskAuth; "===> Setting PSK Auth Type"
0x18001c107  lea     rdx, RasVpnIkeParamTraceInfo
0x18001c10e  mov     rcx, r12
0x18001c111  call    McTemplateU0zjzz_EventWriteTransfer
0x18001c116  mov     dl, cs:byte_1800AA941
0x18001c11c  test    dil, dl
0x18001c11f  jz      short loc_18001C195
0x18001c121  xor     eax, eax
0x18001c123  mov     word ptr [rbp+850h+var_870], ax
0x18001c127  mov     rax, [rbx+70h]
0x18001c12b  test    rax, rax
0x18001c12e  jz      short loc_18001C13A
0x18001c130  cmp     qword ptr [rax+10h], 0
0x18001c135  jz      short loc_18001C13A
0x18001c137  mov     esi, [rax+10h]
0x18001c13a  mov     edx, esi
0x18001c13c  lea     rcx, [rbp+850h+var_870]
0x18001c140  call    ConvertPortNoToString
0x18001c145  test    cs:byte_1800AA941, dil
0x18001c14c  jz      short loc_18001C195
0x18001c14e  mov     rdx, [rbx+70h]
0x18001c152  mov     rax, rdx
0x18001c155  lea     rcx, [rdx+0A7Eh]
0x18001c15c  neg     rax
0x18001c15f  sbb     r8, r8
0x18001c162  and     r8, rcx
0x18001c165  test    rdx, rdx
0x18001c168  lea     r9, [rdx+848h]
0x18001c16f  jnz     short loc_18001C175
0x18001c171  lea     r9, [rbp+850h+var_898]
0x18001c175  lea     rax, [rbp+850h+var_870]
0x18001c179  mov     [rsp+950h+var_928], rax
0x18001c17e  mov     [rsp+950h+var_930], r8
0x18001c183  lea     r8, aPreSharedKeyIs; "Pre-shared key is not specified or empt"...
0x18001c18a  mov     rdx, r14
0x18001c18d  mov     rcx, r12
0x18001c190  call    McTemplateU0zjzz_EventWriteTransfer
0x18001c195  mov     [rsp+950h+var_910], 57h ; 'W'
0x18001c19d  jmp     loc_18001C898
0x18001c1a2  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001c1a9  test    dl, 8
0x18001c1ac  jz      short loc_18001C223
0x18001c1ae  xor     eax, eax
0x18001c1b0  mov     word ptr [rbp+850h+var_870], ax
0x18001c1b4  test    rcx, rcx
0x18001c1b7  jz      short loc_18001C1C4
0x18001c1b9  cmp     [rcx+10h], rax
0x18001c1bd  jz      short loc_18001C1C4
0x18001c1bf  mov     edx, [rcx+10h]
0x18001c1c2  jmp     short loc_18001C1C6
0x18001c1c4  mov     edx, esi
0x18001c1c6  lea     rcx, [rbp+850h+var_870]
0x18001c1ca  call    ConvertPortNoToString
0x18001c1cf  test    cs:byte_1800AA941, 8
0x18001c1d6  jz      short loc_18001C223
0x18001c1d8  mov     rdx, [rbx+70h]
0x18001c1dc  mov     rax, rdx
0x18001c1df  lea     rcx, [rdx+0A7Eh]
0x18001c1e6  neg     rax
0x18001c1e9  sbb     r8, r8
0x18001c1ec  and     r8, rcx
0x18001c1ef  test    rdx, rdx
0x18001c1f2  lea     r9, [rdx+848h]
0x18001c1f9  jnz     short loc_18001C1FF
0x18001c1fb  lea     r9, [rbp+850h+var_898]
0x18001c1ff  lea     rax, [rbp+850h+var_870]
0x18001c203  mov     [rsp+950h+var_928], rax
0x18001c208  mov     [rsp+950h+var_930], r8
  ... truncated ...
```
