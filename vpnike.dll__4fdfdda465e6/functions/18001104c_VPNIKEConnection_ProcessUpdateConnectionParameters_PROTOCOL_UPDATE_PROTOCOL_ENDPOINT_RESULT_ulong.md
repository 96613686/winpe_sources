# VPNIKEConnection::ProcessUpdateConnectionParameters(_PROTOCOL_UPDATE &,_PROTOCOL_ENDPOINT_RESULT &,ulong &)

- ea: `0x18001104c`
- end: `0x18001285c`
- name: `?ProcessUpdateConnectionParameters@VPNIKEConnection@@IEAAKAEAU_PROTOCOL_UPDATE@@AEAU_PROTOCOL_ENDPOINT_RESULT@@AEAK@Z`
- size: `6160`
- prototype: `__int64 __fastcall(VPNIKEConnection *this, struct _PROTOCOL_UPDATE *, struct _PROTOCOL_ENDPOINT_RESULT *, unsigned int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001ca90`
- `0x180025fd0`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18001104c`
- `0x18004b20c`
- `0x18004fca8`
- `0x180066b00`
- `0x180066c0c`
- `0x180066dd0`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x180011789`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x180011789`

## string_xrefs

- `0x180011184`: `VPNIKEConnection::ProcessUpdateConnectionParameters`
- `0x180011c43`: `MobikeUpdate on unknown ip address type`
- `0x180011bbd`: `MobikeUpdate remote address is not part of additional addresses`

## pseudocode

```c
__int64 __fastcall VPNIKEConnection::ProcessUpdateConnectionParameters(
        VPNIKEConnection *this,
        struct _PROTOCOL_UPDATE *a2,
        struct _PROTOCOL_ENDPOINT_RESULT *a3,
        unsigned int *a4)
{
  char v7; // r13
  char v8; // r15
  unsigned int v9; // esi
  char v10; // r8
  __int128 v11; // xmm6
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int128 *v15; // r9
  __int64 v16; // rax
  __int64 v17; // rdx
  __int128 *v18; // r9
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int128 *v24; // r9
  __int64 v25; // rax
  __int64 v26; // rdx
  __int128 *v27; // r9
  const wchar_t *v28; // r8
  __int64 *v29; // rdx
  unsigned int v30; // ebx
  unsigned int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rdx
  __int128 *v35; // r9
  char v36; // di
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rdx
  __int128 *v41; // r9
  __int64 v42; // rdx
  __int128 *v43; // r9
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rax
  __int64 v48; // rax
  IPv4Helper *v49; // rcx
  __int64 v50; // rax
  IPv6Helper *v51; // rcx
  __int64 v52; // rax
  char v53; // al
  int v54; // r9d
  unsigned int v55; // r11d
  __int64 i; // r10
  __int64 v57; // rax
  __int64 v58; // rdx
  __int128 *v59; // r9
  bool v60; // zf
  unsigned int v61; // r10d
  unsigned int j; // edx
  _QWORD *v63; // rcx
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rdx
  __int128 *v68; // r9
  __int64 v69; // rax
  __int64 v70; // rdx
  __int64 v71; // rax
  __int64 v72; // rdx
  int v73; // eax
  __int64 v74; // rcx
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rdx
  __int128 *v80; // r9
  __int64 v81; // rax
  __int64 v82; // rdx
  __int128 *v83; // r9
  __int64 v84; // rax
  __int64 v85; // rdx
  __int128 *v86; // r9
  __int64 v87; // rax
  __int64 v88; // rdx
  __int128 *v89; // r9
  __int64 v90; // rcx
  char v91; // al
  __int64 v92; // rax
  __int64 v93; // rdx
  __int64 v94; // rdx
  __int128 *v95; // r9
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rdx
  __int128 *v99; // r9
  __int64 v100; // rax
  __int64 v101; // rdx
  char v102; // al
  __int64 v103; // rax
  __int64 v104; // rdx
  __int64 v105; // rdx
  __int128 *v106; // r9
  __int64 v107; // rax
  __int64 v108; // rax
  __int64 v109; // rdx
  __int128 *v110; // r9
  __int64 v111; // rax
  __int64 v112; // rdx
  __int64 v113; // rax
  __int64 v114; // rdx
  __int128 *v115; // r9
  __int64 v116; // rax
  __int64 v117; // rdx
  __int128 *v118; // r9
  __int64 v119; // rax
  __int64 v120; // rdx
  __int128 *v121; // r9
  __int64 v122; // rax
  __int64 v123; // rdx
  __int128 *v124; // r9
  struct _PROTOCOL_ENDPOINT_RESULT *v125; // rcx
  struct _PROTOCOL_ENDPOINT_RESULT *v126; // rax
  void *v127; // [rsp+28h] [rbp-E0h]
  unsigned int IfIndex; // [rsp+38h] [rbp-D0h] BYREF
  int v129; // [rsp+3Ch] [rbp-CCh] BYREF
  int v130; // [rsp+40h] [rbp-C8h]
  __int128 v131; // [rsp+48h] [rbp-C0h]
  NET_LUID InterfaceLuid[3]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v133[36]; // [rsp+70h] [rbp-98h] BYREF
  struct _PROTOCOL_ENDPOINT_RESULT *v134; // [rsp+98h] [rbp-70h]
  __int64 v135; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v136; // [rsp+A8h] [rbp-60h]
  __int128 v137; // [rsp+B8h] [rbp-50h]
  __int64 v138; // [rsp+C8h] [rbp-40h]
  int v139; // [rsp+D0h] [rbp-38h]
  int v140; // [rsp+D4h] [rbp-34h]
  __int128 v141; // [rsp+D8h] [rbp-30h] BYREF
  int v142; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v143; // [rsp+ECh] [rbp-1Ch]
  __int128 v144; // [rsp+FCh] [rbp-Ch]
  int v145; // [rsp+10Ch] [rbp+4h]
  int v146; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v147[2044]; // [rsp+11Ch] [rbp+14h] BYREF

  v134 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
  }
  IfIndex = 0;
  v129 = 0;
  v130 = 0;
  LOBYTE(InterfaceLuid[1].Value) = 0;
  *(ULONG64 *)((char *)&InterfaceLuid[1].Value + 1) = 0;
  *(_DWORD *)((char *)&InterfaceLuid[2].Value + 1) = 0;
  *(_WORD *)((char *)&InterfaceLuid[2].Info + 5) = 0;
  *((_BYTE *)&InterfaceLuid[2].Info + 7) = 0;
  v131 = 0u;
  v7 = *((_BYTE *)this + 16);
  v8 = 0;
  v146 = 0;
  memset_0(v147, 0, sizeof(v147));
  v142 = 0;
  v143 = 0;
  v144 = 0;
  v145 = 0;
  v141 = 0;
  v136 = 0;
  v135 = 0;
  v137 = 0;
  v138 = 0;
  v9 = -1;
  v139 = -1;
  v140 = 0;
  v10 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v135,
      L"VPNIKEConnection::ProcessUpdateConnectionParameters",
      &IfIndex,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      *((void **)this + 14));
    v10 = byte_1800AA941;
  }
  if ( !*((_DWORD *)a2 + 4) )
    goto LABEL_76;
  v11 = 0;
  memset(&v133[10], 0, 26);
  if ( *((_DWORD *)a2 + 4) == 1 )
  {
    if ( *((_DWORD *)a2 + 5) && *((_WORD *)a2 + 10) != 0xFEA9 && *((_BYTE *)a2 + 20) != 127 )
    {
      if ( (v10 & 8) != 0 )
      {
        LOWORD(v142) = 0;
        v12 = *((_QWORD *)this + 14);
        if ( v12 && *(_QWORD *)(v12 + 16) )
          v13 = *(unsigned int *)(v12 + 16);
        else
          v13 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v142, v13);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v14 = *((_QWORD *)this + 14);
          LODWORD(v15) = v14 + 2120;
          if ( !v14 )
            v15 = &v141;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"Processing mobike request using local end point address.Retrieving interface index...",
            (_DWORD)v15,
            (v14 + 2686) & -(__int64)(v14 != 0),
            (__int64)&v142);
        }
      }
      *(_WORD *)&v133[8] = 2;
      *(_DWORD *)&v133[12] = *((_DWORD *)a2 + 5);
LABEL_47:
      *(_OWORD *)&v133[20] = v11;
      IfIndex = GetIfIndex(&v133[8], a4);
      if ( IfIndex )
      {
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_58;
        LOWORD(v142) = 0;
        v25 = *((_QWORD *)this + 14);
        if ( v25 && *(_QWORD *)(v25 + 16) )
          v9 = *(_DWORD *)(v25 + 16);
        ConvertPortNoToString(&v142, v9);
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_58;
        v26 = *((_QWORD *)this + 14);
        LODWORD(v27) = v26 + 2120;
        if ( !v26 )
          v27 = &v141;
        v127 = (void *)((v26 + 2686) & -(__int64)(v26 != 0));
        v28 = L"Failed to retrieve the interface index of the local end point address ";
        goto LABEL_56;
      }
      v32 = *a4;
      if ( *((_DWORD *)a2 + 3) )
      {
        if ( v32 != *((_DWORD *)a2 + 3) )
        {
          if ( (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v146) = 0;
            LOWORD(v142) = 0;
            v33 = *((_QWORD *)this + 14);
            if ( v33 && *(_QWORD *)(v33 + 16) )
              v9 = *(_DWORD *)(v33 + 16);
            ConvertPortNoToString(&v142, v9);
            FormatRRASErrorString(
              &v146,
              L"The interface index passed (%d) does match the interface index (%d) on which the passed local address is",
              *((unsigned int *)a2 + 3),
              *a4);
LABEL_70:
            if ( (byte_1800AA941 & 4) != 0 )
            {
              v34 = *((_QWORD *)this + 14);
              LODWORD(v35) = v34 + 2120;
              if ( !v34 )
                v35 = &v141;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceError,
                (unsigned int)&v146,
                (_DWORD)v35,
                (v34 + 2686) & -(__int64)(v34 != 0),
                (__int64)&v142);
            }
            goto LABEL_352;
          }
          goto LABEL_352;
        }
      }
      else
      {
        *((_DWORD *)a2 + 3) = v32;
      }
      v8 = 1;
      v10 = byte_1800AA941;
LABEL_76:
      v36 = 0;
      if ( *((_DWORD *)a2 + 3) )
      {
        if ( (v10 & 8) != 0 )
        {
          LOWORD(v146) = 0;
          LOWORD(v142) = 0;
          v37 = *((_QWORD *)this + 14);
          if ( v37 && *(_QWORD *)(v37 + 16) )
            v38 = *(unsigned int *)(v37 + 16);
          else
            v38 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v142, v38);
          FormatRRASErrorString(&v146, L"Processing mobike request using interface index %d", *((unsigned int *)a2 + 3));
          if ( (byte_1800AA941 & 8) != 0 )
          {
            v42 = *((_QWORD *)this + 14);
            LODWORD(v43) = v42 + 2120;
            if ( !v42 )
              v43 = &v141;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceInfo,
              (unsigned int)&v146,
              (_DWORD)v43,
              (v42 + 2686) & -(__int64)(v42 != 0),
              (__int64)&v142);
          }
        }
        InterfaceLuid[0].Value = 0;
        IfIndex = ConvertInterfaceIndexToLuid(*((_DWORD *)a2 + 3), InterfaceLuid);
        if ( IfIndex )
        {
          if ( (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v146) = 0;
            LOWORD(v142) = 0;
            v47 = *((_QWORD *)this + 14);
            if ( v47 && *(_QWORD *)(v47 + 16) )
              v9 = *(_DWORD *)(v47 + 16);
            ConvertPortNoToString(&v142, v9);
            FormatRRASErrorString(&v146, L"InterfaceIndex [%d] is invalid", *((unsigned int *)a2 + 3));
            goto LABEL_70;
          }
LABEL_352:
          IfIndex = 87;
          goto LABEL_58;
        }
        if ( *((unsigned __int16 *)&InterfaceLuid[0].Info + 3) == 24 )
        {
          if ( (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v146) = 0;
            LOWORD(v142) = 0;
            v48 = *((_QWORD *)this + 14);
            if ( v48 && *(_QWORD *)(v48 + 16) )
              v9 = *(_DWORD *)(v48 + 16);
            ConvertPortNoToString(&v142, v9);
            FormatRRASErrorString(
              &v146,
              L"InterfaceIndex [%d] is invalid. IfType is IF_TYPE_SOFTWARE_LOOPBACK",
              *((unsigned int *)a2 + 3));
            goto LABEL_70;
          }
          goto LABEL_352;
        }
        v49 = (IPv4Helper *)*((_QWORD *)this + 4);
        if ( v49 && IPv4Helper::DoNegotiate(v49, v44, v45, v46) )
        {
          if ( *(_QWORD *)(*((_QWORD *)this + 4) + 48LL) == InterfaceLuid[0].Value )
          {
            if ( (byte_1800AA941 & 4) != 0 )
            {
              LOWORD(v146) = 0;
              LOWORD(v142) = 0;
              v50 = *((_QWORD *)this + 14);
              if ( v50 && *(_QWORD *)(v50 + 16) )
                v9 = *(_DWORD *)(v50 + 16);
              ConvertPortNoToString(&v142, v9);
              FormatRRASErrorString(
                &v146,
                L"InterfaceIndex [%d] is same as current VPN ipv4 interface which is invalid",
                *((unsigned int *)a2 + 3));
              goto LABEL_70;
            }
            goto LABEL_352;
          }
        }
        else
        {
          v51 = (IPv6Helper *)*((_QWORD *)this + 5);
          if ( !v51 || !IPv6Helper::DoNegotiate(v51, v44, v45, v46) )
          {
            if ( (byte_1800AA941 & 4) != 0 )
            {
              LOWORD(v142) = 0;
              v57 = *((_QWORD *)this + 14);
              if ( v57 && *(_QWORD *)(v57 + 16) )
                v9 = *(_DWORD *)(v57 + 16);
              ConvertPortNoToString(&v142, v9);
              if ( (byte_1800AA941 & 4) != 0 )
              {
                v58 = *((_QWORD *)this + 14);
                LODWORD(v59) = v58 + 2120;
                if ( !v58 )
                  v59 = &v141;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasVpnIkeParamTraceError,
                  (unsigned int)L"None of the interfaces (v4/v6) are enabled",
                  (_DWORD)v59,
                  (v58 + 2686) & -(__int64)(v58 != 0),
                  (__int64)&v142);
              }
            }
            goto LABEL_352;
          }
          if ( *(_QWORD *)(*((_QWORD *)this + 5) + 120LL) == InterfaceLuid[0].Value )
          {
            if ( (byte_1800AA941 & 4) != 0 )
            {
              LOWORD(v146) = 0;
              LOWORD(v142) = 0;
              v52 = *((_QWORD *)this + 14);
              if ( v52 && *(_QWORD *)(v52 + 16) )
                v9 = *(_DWORD *)(v52 + 16);
              ConvertPortNoToString(&v142, v9);
              FormatRRASErrorString(
                &v146,
                L"InterfaceIndex [%d] is same as current VPN ipv6 interface which is invalid",
                *((unsigned int *)a2 + 3));
              goto LABEL_70;
            }
            goto LABEL_352;
          }
        }
        *a4 = *((_DWORD *)a2 + 3);
        v36 = 1;
        v10 = byte_1800AA941;
      }
      v53 = 0;
      v54 = *((_DWORD *)a2 + 9);
      switch ( v54 )
      {
        case 0:
LABEL_159:
          if ( v36 && v53 )
          {
            if ( v8 )
            {
              if ( *((_DWORD *)a2 + 4) != v54 )
              {
                if ( (v10 & 4) != 0 )
                {
                  LOWORD(v146) = 0;
                  LOWORD(v142) = 0;
                  v66 = *((_QWORD *)this + 14);
                  if ( v66 && *(_QWORD *)(v66 + 16) )
                    v9 = *(_DWORD *)(v66 + 16);
                  ConvertPortNoToString(&v142, v9);
                  FormatRRASErrorString(
                    &v146,
                    L"Local end point and remote end point IP types do not match.Local end point type is %d. Remote end point type is %d",
                    *((unsigned int *)a2 + 4),
                    *((unsigned int *)a2 + 9));
                  if ( (byte_1800AA941 & 4) != 0 )
                  {
                    v67 = *((_QWORD *)this + 14);
                    LODWORD(v68) = v67 + 2120;
                    if ( !v67 )
                      v68 = &v141;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasVpnIkeParamTraceError,
                      (unsigned int)&v146,
                      (_DWORD)v68,
                      (v67 + 2686) & -(__int64)(v67 != 0),
                      (__int64)&v142);
                  }
                }
                IfIndex = 13;
                goto LABEL_58;
              }
              v7 = v54 == 1;
              if ( v54 != 1 )
              {
                *(_OWORD *)&InterfaceLuid[1].Value = *(_OWORD *)((char *)a2 + 20);
                v131 = *(_OWORD *)((char *)a2 + 40);
                goto LABEL_364;
              }
              v129 = *((_DWORD *)a2 + 5);
              v73 = *((_DWORD *)a2 + 10);
              goto LABEL_285;
            }
            v74 = *a4;
            if ( v54 == 1 )
            {
              IfIndex = GetIPv4AddressFromIndex(v74, &v129, InterfaceLuid);
              if ( IfIndex )
              {
                if ( (byte_1800AA941 & 4) == 0 )
                  goto LABEL_58;
                LOWORD(v146) = 0;
                LOWORD(v142) = 0;
                v75 = *((_QWORD *)this + 14);
                if ( v75 && *(_QWORD *)(v75 + 16) )
                  v9 = *(_DWORD *)(v75 + 16);
                ConvertPortNoToString(&v142, v9);
                FormatRRASErrorString(&v146, L"GetIPv4AddressFromIndex failed. Error: %d", IfIndex);
                goto LABEL_198;
              }
              v130 = *((_DWORD *)a2 + 10);
              goto LABEL_312;
            }
            IfIndex = GetIPv6AddressFromIndex(v74, &InterfaceLuid[1], InterfaceLuid);
            if ( IfIndex )
            {
              if ( (byte_1800AA941 & 4) == 0 )
                goto LABEL_58;
              LOWORD(v146) = 0;
              LOWORD(v142) = 0;
              v77 = *((_QWORD *)this + 14);
              if ( v77 && *(_QWORD *)(v77 + 16) )
                v9 = *(_DWORD *)(v77 + 16);
              ConvertPortNoToString(&v142, v9);
              FormatRRASErrorString(&v146, L"GetIPv6AddressFromIndex failed. Error: %d", IfIndex);
              goto LABEL_198;
            }
            v131 = *(_OWORD *)((char *)a2 + 40);
LABEL_274:
            v7 = 0;
            goto LABEL_364;
          }
          if ( v8 )
          {
            if ( v7 )
            {
              if ( *((_DWORD *)a2 + 4) != 1 )
              {
                if ( (v10 & 4) != 0 )
                {
                  LOWORD(v142) = 0;
                  v81 = *((_QWORD *)this + 14);
                  if ( v81 && *(_QWORD *)(v81 + 16) )
                    v9 = *(_DWORD *)(v81 + 16);
                  ConvertPortNoToString(&v142, v9);
                  if ( (byte_1800AA941 & 4) != 0 )
                  {
                    v82 = *((_QWORD *)this + 14);
                    LODWORD(v83) = v82 + 2120;
                    if ( !v82 )
                      v83 = &v141;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasVpnIkeParamTraceError,
                      (unsigned int)L"No mobike possible. Remote end point unspecified. Tunnel type is IPV4 ",
                      (_DWORD)v83,
                      (v82 + 2686) & -(__int64)(v82 != 0),
                      (__int64)&v142);
                  }
                }
                goto LABEL_352;
              }
              v129 = *((_DWORD *)a2 + 5);
              v130 = *((_DWORD *)this + 17);
              if ( (v10 & 8) != 0 )
              {
                LOWORD(v142) = 0;
                v78 = *((_QWORD *)this + 14);
                if ( v78 && *(_QWORD *)(v78 + 16) )
                  v9 = *(_DWORD *)(v78 + 16);
                ConvertPortNoToString(&v142, v9);
                if ( (byte_1800AA941 & 8) != 0 )
                {
                  v79 = *((_QWORD *)this + 14);
                  LODWORD(v80) = v79 + 2120;
                  if ( !v79 )
                    v80 = &v141;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasVpnIkeParamTraceInfo,
                    (unsigned int)L"Remote end point address is unspecified.Using the current remote endpoint address!",
                    (_DWORD)v80,
                    (v79 + 2686) & -(__int64)(v79 != 0),
                    (__int64)&v142);
                }
              }
            }
            else
            {
              if ( *((_DWORD *)a2 + 4) != 2 )
              {
                if ( (v10 & 4) != 0 )
                {
                  LOWORD(v142) = 0;
                  v87 = *((_QWORD *)this + 14);
                  if ( v87 && *(_QWORD *)(v87 + 16) )
                    v9 = *(_DWORD *)(v87 + 16);
                  ConvertPortNoToString(&v142, v9);
                  if ( (byte_1800AA941 & 4) != 0 )
                  {
                    v88 = *((_QWORD *)this + 14);
                    LODWORD(v89) = v88 + 2120;
                    if ( !v88 )
                      v89 = &v141;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasVpnIkeParamTraceError,
                      (unsigned int)L"No mobike possible. Remote end point unspecified. Tunnel type is IPV6",
                      (_DWORD)v89,
                      (v88 + 2686) & -(__int64)(v88 != 0),
                      (__int64)&v142);
                  }
                }
                goto LABEL_352;
              }
              *(_OWORD *)&InterfaceLuid[1].Value = *(_OWORD *)((char *)a2 + 20);
              v131 = *(_OWORD *)((char *)this + 72);
              if ( (v10 & 8) != 0 )
              {
                LOWORD(v142) = 0;
                v84 = *((_QWORD *)this + 14);
                if ( v84 && *(_QWORD *)(v84 + 16) )
                  v9 = *(_DWORD *)(v84 + 16);
                ConvertPortNoToString(&v142, v9);
                if ( (byte_1800AA941 & 8) != 0 )
                {
                  v85 = *((_QWORD *)this + 14);
                  LODWORD(v86) = v85 + 2120;
                  if ( !v85 )
                    v86 = &v141;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasVpnIkeParamTraceInfo,
                    (unsigned int)L"Remote end point address is unspecified.Using the current remote endpoint address",
                    (_DWORD)v86,
                    (v85 + 2686) & -(__int64)(v85 != 0),
                    (__int64)&v142);
                }
              }
            }
            goto LABEL_364;
          }
          if ( !v36 )
          {
            if ( v53 )
            {
              if ( v7 )
              {
                if ( v54 != 1 )
                {
                  if ( (v10 & 4) != 0 )
                  {
                    LOWORD(v142) = 0;
                    v116 = *((_QWORD *)this + 14);
                    if ( v116 && *(_QWORD *)(v116 + 16) )
                      v9 = *(_DWORD *)(v116 + 16);
                    ConvertPortNoToString(&v142, v9);
                    if ( (byte_1800AA941 & 4) != 0 )
                    {
                      v117 = *((_QWORD *)this + 14);
                      LODWORD(v118) = v117 + 2120;
                      if ( !v117 )
                        v118 = &v141;
                      McTemplateU0zjzz_EventWriteTransfer(
                        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        (unsigned int)RasVpnIkeParamTraceError,
                        (unsigned int)L"No mobike possible. Local end point unspecified. Tunnel type is IPV4",
                        (_DWORD)v118,
                        (v117 + 2686) & -(__int64)(v117 != 0),
                        (__int64)&v142);
                    }
                  }
                  goto LABEL_352;
                }
                v129 = *((_DWORD *)this + 12);
                v130 = *((_DWORD *)a2 + 10);
              }
              else
              {
                if ( v54 != 2 )
                {
                  if ( (v10 & 4) != 0 )
                  {
                    LOWORD(v142) = 0;
                    v119 = *((_QWORD *)this + 14);
                    if ( v119 && *(_QWORD *)(v119 + 16) )
                      v9 = *(_DWORD *)(v119 + 16);
                    ConvertPortNoToString(&v142, v9);
                    if ( (byte_1800AA941 & 4) != 0 )
                    {
                      v120 = *((_QWORD *)this + 14);
                      LODWORD(v121) = v120 + 2120;
                      if ( !v120 )
                        v121 = &v141;
                      McTemplateU0zjzz_EventWriteTransfer(
                        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        (unsigned int)RasVpnIkeParamTraceError,
                        (unsigned int)L"No mobike possible. Local end point unspecified. Tunnel type is IPV6",
                        (_DWORD)v121,
                        (v120 + 2686) & -(__int64)(v120 != 0),
                        (__int64)&v142);
                    }
                  }
                  goto LABEL_352;
                }
                *(_OWORD *)&InterfaceLuid[1].Value = *(_OWORD *)((char *)this + 52);
                v131 = *(_OWORD *)((char *)a2 + 40);
              }
              if ( (v10 & 8) != 0 )
              {
                LOWORD(v142) = 0;
                v113 = *((_QWORD *)this + 14);
                if ( v113 && *(_QWORD *)(v113 + 16) )
                  v9 = *(_DWORD *)(v113 + 16);
                ConvertPortNoToString(&v142, v9);
                if ( (byte_1800AA941 & 8) != 0 )
                {
                  v114 = *((_QWORD *)this + 14);
                  LODWORD(v115) = v114 + 2120;
                  if ( !v114 )
                    v115 = &v141;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasVpnIkeParamTraceInfo,
                    (unsigned int)L"Local end point address is unspecified.Using the current local endpoint address",
                    (_DWORD)v115,
                    (v114 + 2686) & -(__int64)(v114 != 0),
                    (__int64)&v142);
                }
              }
            }
            else
            {
              *a4 = *((_DWORD *)this + 27);
              if ( v7 )
              {
                v129 = *((_DWORD *)this + 12);
                v130 = *((_DWORD *)this + 17);
              }
              else
              {
                *(_OWORD *)&InterfaceLuid[1].Value = *(_OWORD *)((char *)this + 52);
                v131 = *(_OWORD *)((char *)this + 72);
              }
              if ( (byte_1800AA941 & 8) != 0 )
              {
                LOWORD(v146) = 0;
                LOWORD(v142) = 0;
                v122 = *((_QWORD *)this + 14);
                if ( v122 && *(_QWORD *)(v122 + 16) )
                  v9 = *(_DWORD *)(v122 + 16);
                ConvertPortNoToString(&v142, v9);
                FormatRRASErrorString(
                  &v146,
                  L"Local end point and remote end point address are unspecified.Using the current local end point address"
                   " and remote endpoint address and interface index %d ",
                  *a4);
                if ( (byte_1800AA941 & 8) != 0 )
                {
                  v123 = *((_QWORD *)this + 14);
                  LODWORD(v124) = v123 + 2120;
                  if ( !v123 )
                    v124 = &v141;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasVpnIkeParamTraceInfo,
                    (unsigned int)&v146,
                    (_DWORD)v124,
                    (v123 + 2686) & -(__int64)(*((_QWORD *)this + 14) != 0),
                    (__int64)&v142);
                }
              }
            }
            goto LABEL_364;
          }
          v90 = *((unsigned int *)a2 + 3);
          if ( v7 )
          {
            IfIndex = GetIPv4AddressFromIndex(v90, &v129, InterfaceLuid);
            if ( !IfIndex )
            {
              v73 = *((_DWORD *)this + 17);
LABEL_285:
              v130 = v73;
              goto LABEL_364;
            }
            v91 = byte_1800AA941;
            if ( (byte_1800AA941 & 4) != 0 )
            {
              LOWORD(v146) = 0;
              LOWORD(v142) = 0;
              v92 = *((_QWORD *)this + 14);
              if ( v92 && *(_QWORD *)(v92 + 16) )
                v93 = *(unsigned int *)(v92 + 16);
              else
                v93 = 0xFFFFFFFFLL;
              ConvertPortNoToString(&v142, v93);
              FormatRRASErrorString(&v146, L"GetIPv4AddressFromIndex failed: %d", IfIndex);
              v91 = byte_1800AA941;
              if ( (byte_1800AA941 & 4) != 0 )
              {
                v94 = *((_QWORD *)this + 14);
                LODWORD(v95) = v94 + 2120;
                if ( !v94 )
                  v95 = &v141;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasVpnIkeParamTraceError,
                  (unsigned int)&v146,
                  (_DWORD)v95,
                  (v94 + 2686) & -(__int64)(v94 != 0),
                  (__int64)&v142);
                v91 = byte_1800AA941;
              }
            }
            if ( *((_DWORD *)this + 75) )
            {
              IfIndex = GetIPv6AddressFromIndex(*((unsigned int *)a2 + 3), &InterfaceLuid[1], InterfaceLuid);
              if ( !IfIndex )
              {
                if ( (byte_1800AA941 & 8) != 0 )
                {
                  LOWORD(v142) = 0;
                  v97 = *((_QWORD *)this + 14);
                  if ( v97 && *(_QWORD *)(v97 + 16) )
                    v9 = *(_DWORD *)(v97 + 16);
                  ConvertPortNoToString(&v142, v9);
                  if ( (byte_1800AA941 & 8) != 0 )
                  {
                    v98 = *((_QWORD *)this + 14);
                    LODWORD(v99) = v98 + 2120;
                    if ( !v98 )
                      v99 = &v141;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasVpnIkeParamTraceInfo,
                      (unsigned int)L"Tunnel is switching from v4 to v6",
                      (_DWORD)v99,
                      (v98 + 2686) & -(__int64)(v98 != 0),
                      (__int64)&v142);
                  }
                }
                v131 = *(_OWORD *)*((_QWORD *)this + 39);
                goto LABEL_274;
              }
              if ( (byte_1800AA941 & 4) == 0 )
                goto LABEL_58;
              LOWORD(v146) = 0;
              LOWORD(v142) = 0;
              v96 = *((_QWORD *)this + 14);
              if ( v96 && *(_QWORD *)(v96 + 16) )
                v9 = *(_DWORD *)(v96 + 16);
              ConvertPortNoToString(&v142, v9);
              FormatRRASErrorString(&v146, L"Trying to get GetIPv6AddressFromIndex. Error: %d", IfIndex);
LABEL_198:
              if ( (byte_1800AA941 & 4) == 0 )
                goto LABEL_58;
              v76 = *((_QWORD *)this + 14);
              LODWORD(v27) = v76 + 2120;
              if ( !v76 )
                v27 = &v141;
              v127 = (void *)((v76 + 2686) & -(__int64)(v76 != 0));
              v28 = (const wchar_t *)&v146;
              goto LABEL_56;
            }
            if ( (v91 & 8) == 0 )
              goto LABEL_58;
            LOWORD(v142) = 0;
            v100 = *((_QWORD *)this + 14);
            if ( v100 && *(_QWORD *)(v100 + 16) )
              v9 = *(_DWORD *)(v100 + 16);
            ConvertPortNoToString(&v142, v9);
            if ( (byte_1800AA941 & 8) == 0 )
              goto LABEL_58;
            v101 = *((_QWORD *)this + 14);
            LODWORD(v27) = v101 + 2120;
            if ( !v101 )
              v27 = &v141;
            v127 = (void *)((v101 + 2686) & -(__int64)(v101 != 0));
            v28 = L"v4 Address failed, and no v6 server address available to try";
          }
          else
          {
            IfIndex = GetIPv6AddressFromIndex(v90, &InterfaceLuid[1], InterfaceLuid);
            if ( !IfIndex )
            {
              v131 = *(_OWORD *)((char *)this + 72);
LABEL_364:
              if ( v7 )
              {
                v125 = v134;
                *(_DWORD *)v134 = 1;
                *((_DWORD *)v125 + 1) = v129;
                *((_DWORD *)v125 + 5) = 1;
                *((_DWORD *)v125 + 6) = v130;
              }
              else
              {
                v126 = v134;
                *(_DWORD *)v134 = 2;
                *(_OWORD *)((char *)v126 + 4) = *(_OWORD *)&InterfaceLuid[1].Value;
                *((_DWORD *)v126 + 5) = 2;
                *(_OWORD *)((char *)v126 + 24) = v131;
              }
              goto LABEL_58;
            }
            v102 = byte_1800AA941;
            if ( (byte_1800AA941 & 4) != 0 )
            {
              LOWORD(v146) = 0;
              LOWORD(v142) = 0;
              v103 = *((_QWORD *)this + 14);
              if ( v103 && *(_QWORD *)(v103 + 16) )
                v104 = *(unsigned int *)(v103 + 16);
              else
                v104 = 0xFFFFFFFFLL;
              ConvertPortNoToString(&v142, v104);
              FormatRRASErrorString(&v146, L"GetIPv6AddressFromIndex failed: %d", IfIndex);
              v102 = byte_1800AA941;
              if ( (byte_1800AA941 & 4) != 0 )
              {
                v105 = *((_QWORD *)this + 14);
                LODWORD(v106) = v105 + 2120;
                if ( !v105 )
                  v106 = &v141;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasVpnIkeParamTraceError,
                  (unsigned int)&v146,
                  (_DWORD)v106,
                  (v105 + 2686) & -(__int64)(v105 != 0),
                  (__int64)&v142);
                v102 = byte_1800AA941;
              }
            }
            if ( *((_DWORD *)this + 74) )
            {
              IfIndex = GetIPv4AddressFromIndex(*((unsigned int *)a2 + 3), &v129, InterfaceLuid);
              if ( !IfIndex )
              {
                if ( (byte_1800AA941 & 8) != 0 )
                {
                  LOWORD(v142) = 0;
                  v108 = *((_QWORD *)this + 14);
                  if ( v108 && *(_QWORD *)(v108 + 16) )
                    v9 = *(_DWORD *)(v108 + 16);
                  ConvertPortNoToString(&v142, v9);
                  if ( (byte_1800AA941 & 8) != 0 )
                  {
                    v109 = *((_QWORD *)this + 14);
                    LODWORD(v110) = v109 + 2120;
                    if ( !v109 )
                      v110 = &v141;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasVpnIkeParamTraceInfo,
                      (unsigned int)L"Tunnel is switching from v6 to v4",
                      (_DWORD)v110,
                      (v109 + 2686) & -(__int64)(v109 != 0),
                      (__int64)&v142);
                  }
                }
                v130 = **((_DWORD **)this + 38);
LABEL_312:
                v7 = 1;
                goto LABEL_364;
              }
              if ( (byte_1800AA941 & 4) == 0 )
                goto LABEL_58;
              LOWORD(v146) = 0;
              LOWORD(v142) = 0;
              v107 = *((_QWORD *)this + 14);
              if ( v107 && *(_QWORD *)(v107 + 16) )
                v9 = *(_DWORD *)(v107 + 16);
              ConvertPortNoToString(&v142, v9);
              FormatRRASErrorString(&v146, L"Trying to get GetIPv4AddressFromIndex. Error: %d", IfIndex);
              goto LABEL_198;
            }
            if ( (v102 & 8) == 0 )
              goto LABEL_58;
            LOWORD(v142) = 0;
            v111 = *((_QWORD *)this + 14);
            if ( v111 && *(_QWORD *)(v111 + 16) )
              v9 = *(_DWORD *)(v111 + 16);
            ConvertPortNoToString(&v142, v9);
            if ( (byte_1800AA941 & 8) == 0 )
              goto LABEL_58;
            v112 = *((_QWORD *)this + 14);
            LODWORD(v27) = v112 + 2120;
            if ( !v112 )
              v27 = &v141;
            v127 = (void *)((v112 + 2686) & -(__int64)(v112 != 0));
            v28 = L"v6 Address failed, and no v4 server address available to try";
          }
          v29 = RasVpnIkeParamTraceInfo;
          goto LABEL_57;
        case 1:
          v55 = *((_DWORD *)this + 74);
          if ( v55 )
          {
            for ( i = 0; (unsigned int)i < v55; i = (unsigned int)(i + 1) )
            {
              if ( *(_DWORD *)(*((_QWORD *)this + 38) + 4 * i) == *((_DWORD *)a2 + 10) )
                goto LABEL_158;
            }
            goto LABEL_172;
          }
          if ( !*((_BYTE *)this + 16) )
            goto LABEL_172;
          v60 = *((_DWORD *)this + 17) == *((_DWORD *)a2 + 10);
          break;
        case 2:
          v61 = *((_DWORD *)this + 75);
          if ( v61 )
          {
            for ( j = 0; j < v61; ++j )
            {
              v63 = (_QWORD *)(*((_QWORD *)this + 39) + 16LL * j);
              v64 = *v63 - *((_QWORD *)a2 + 5);
              if ( *v63 == *((_QWORD *)a2 + 5) )
                v64 = v63[1] - *((_QWORD *)a2 + 6);
              if ( !v64 )
                goto LABEL_158;
            }
            goto LABEL_172;
          }
          if ( *((_BYTE *)this + 16) )
            goto LABEL_172;
          v65 = *((_QWORD *)this + 9) - *((_QWORD *)a2 + 5);
          if ( !v65 )
            v65 = *((_QWORD *)this + 10) - *((_QWORD *)a2 + 6);
          v60 = v65 == 0;
          break;
        default:
          IfIndex = 87;
          if ( (v10 & 4) == 0 )
            goto LABEL_58;
          LOWORD(v142) = 0;
          v71 = *((_QWORD *)this + 14);
          if ( v71 && *(_QWORD *)(v71 + 16) )
            v9 = *(_DWORD *)(v71 + 16);
          ConvertPortNoToString(&v142, v9);
          if ( (byte_1800AA941 & 4) == 0 )
            goto LABEL_58;
          v72 = *((_QWORD *)this + 14);
          LODWORD(v27) = v72 + 2120;
          if ( !v72 )
            v27 = &v141;
          v127 = (void *)((v72 + 2686) & -(__int64)(v72 != 0));
          v28 = L"MobikeUpdate on unknown ip address type";
LABEL_56:
          v29 = RasVpnIkeParamTraceError;
LABEL_57:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (_DWORD)v29,
            (_DWORD)v28,
            (_DWORD)v27,
            (__int64)v127,
            (__int64)&v142);
          goto LABEL_58;
      }
      if ( v60 )
      {
LABEL_158:
        v53 = 1;
        goto LABEL_159;
      }
LABEL_172:
      IfIndex = 87;
      if ( (v10 & 4) == 0 )
        goto LABEL_58;
      LOWORD(v142) = 0;
      v69 = *((_QWORD *)this + 14);
      if ( v69 && *(_QWORD *)(v69 + 16) )
        v9 = *(_DWORD *)(v69 + 16);
      ConvertPortNoToString(&v142, v9);
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_58;
      v70 = *((_QWORD *)this + 14);
      LODWORD(v27) = v70 + 2120;
      if ( !v70 )
        v27 = &v141;
      v127 = (void *)((v70 + 2686) & -(__int64)(v70 != 0));
      v28 = L"MobikeUpdate remote address is not part of additional addresses";
      goto LABEL_56;
    }
    if ( (v10 & 4) != 0 )
    {
      LOWORD(v142) = 0;
      v16 = *((_QWORD *)this + 14);
      if ( v16 && *(_QWORD *)(v16 + 16) )
        v9 = *(_DWORD *)(v16 + 16);
      ConvertPortNoToString(&v142, v9);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v17 = *((_QWORD *)this + 14);
        LODWORD(v18) = v17 + 2120;
        if ( !v17 )
          v18 = &v141;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Invalid local address specified.",
          (_DWORD)v18,
          (v17 + 2686) & -(__int64)(v17 != 0),
          (__int64)&v142);
      }
    }
    IfIndex = 87;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v20 = 105;
LABEL_34:
        WPP_SF_d(v19[2], v20, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, 87);
        goto LABEL_58;
      }
      goto LABEL_58;
    }
  }
  else
  {
    if ( (*((_BYTE *)a2 + 20) & 0xF0) != 0 && (*((_BYTE *)a2 + 20) & 0xF0) != 0xF0 )
    {
      if ( (v10 & 8) != 0 )
      {
        LOWORD(v142) = 0;
        v21 = *((_QWORD *)this + 14);
        if ( v21 && *(_QWORD *)(v21 + 16) )
          v22 = *(unsigned int *)(v21 + 16);
        else
          v22 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v142, v22);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v23 = *((_QWORD *)this + 14);
          LODWORD(v24) = v23 + 2120;
          if ( !v23 )
            v24 = &v141;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"Processing mobike request using local end point address.Retrieving interface index...",
            (_DWORD)v24,
            (v23 + 2686) & -(__int64)(v23 != 0),
            (__int64)&v142);
        }
      }
      *(_WORD *)&v133[8] = 23;
      *(_OWORD *)&v133[16] = *(_OWORD *)((char *)a2 + 20);
      v11 = *(_OWORD *)&v133[20];
      goto LABEL_47;
    }
    if ( (v10 & 4) != 0 )
    {
      LOWORD(v142) = 0;
      v39 = *((_QWORD *)this + 14);
      if ( v39 && *(_QWORD *)(v39 + 16) )
        v9 = *(_DWORD *)(v39 + 16);
      ConvertPortNoToString(&v142, v9);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v40 = *((_QWORD *)this + 14);
        LODWORD(v41) = v40 + 2120;
        if ( !v40 )
          v41 = &v141;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Invalid local address specified .",
          (_DWORD)v41,
          (v40 + 2686) & -(__int64)(v40 != 0),
          (__int64)&v142);
      }
    }
    IfIndex = 87;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v20 = 106;
        goto LABEL_34;
      }
LABEL_58:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, IfIndex);
      }
    }
  }
  v30 = IfIndex;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v135);
  return v30;
}

```

## disassembly

```asm
0x18001104c  mov     rax, rsp
0x18001104f  push    rbp
0x180011050  push    rbx
0x180011051  push    rsi
0x180011052  push    rdi
0x180011053  push    r12
0x180011055  push    r13
0x180011057  push    r14
0x180011059  push    r15
0x18001105b  lea     rbp, [rax-878h]
0x180011062  sub     rsp, 938h
0x180011069  movaps  xmmword ptr [rax-58h], xmm6
0x18001106d  mov     rax, cs:__security_cookie
0x180011074  xor     rax, rsp
0x180011077  mov     [rbp+870h+var_60], rax
0x18001107e  mov     r12, r9
0x180011081  mov     [rbp+870h+var_8E0], r8
0x180011085  mov     r14, rdx
0x180011088  mov     rbx, rcx
0x18001108b  lea     rax, WPP_GLOBAL_Control
0x180011092  mov     rcx, cs:WPP_GLOBAL_Control
0x180011099  cmp     rcx, rax
0x18001109c  jz      short loc_1800110BF
0x18001109e  test    byte ptr [rcx+1Ch], 1
0x1800110a2  jz      short loc_1800110BF
0x1800110a4  cmp     byte ptr [rcx+19h], 6
0x1800110a8  jb      short loc_1800110BF
0x1800110aa  mov     edx, 68h ; 'h'
0x1800110af  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x1800110b6  mov     rcx, [rcx+10h]
0x1800110ba  call    WPP_SF_
0x1800110bf  mov     [rsp+970h+var_940], 0
0x1800110c7  mov     byte ptr [rsp+970h+var_93C], 0
0x1800110cc  xor     eax, eax
0x1800110ce  mov     word ptr [rsp+970h+var_93C+1], ax
0x1800110d3  mov     byte ptr [rsp+970h+var_93C+3], al
0x1800110d7  mov     byte ptr [rsp+970h+var_938], al
0x1800110db  mov     word ptr [rsp+970h+var_938+1], ax
0x1800110e0  mov     byte ptr [rsp+970h+var_938+3], al
0x1800110e4  mov     [rsp+970h+InterfaceLuid+8], al
0x1800110e8  mov     qword ptr [rsp+970h+InterfaceLuid+9], rax
0x1800110ed  mov     dword ptr [rsp+970h+InterfaceLuid+11h], eax
0x1800110f1  mov     word ptr [rsp+970h+InterfaceLuid+15h], ax
0x1800110f6  mov     [rsp+970h+InterfaceLuid+17h], al
0x1800110fa  mov     byte ptr [rsp+970h+var_938+8], al
0x1800110fe  mov     qword ptr [rsp+970h+var_938+9], rax
0x180011103  mov     dword ptr [rsp+970h+var_928+1], eax
0x180011107  mov     word ptr [rsp+970h+var_928+5], ax
0x18001110c  mov     byte ptr [rsp+970h+var_928+7], al
0x180011110  mov     r13b, [rbx+10h]
0x180011114  xor     r15b, r15b
0x180011117  mov     [rbp+870h+var_860], eax
0x18001111a  xor     edx, edx; Val
0x18001111c  mov     r8d, 7FCh; Size
0x180011122  lea     rcx, [rbp+870h+var_85C]; void *
0x180011126  call    memset_0
0x18001112b  xor     eax, eax
0x18001112d  mov     [rbp+870h+var_890], eax
0x180011130  xorps   xmm0, xmm0
0x180011133  movups  [rbp+870h+var_88C], xmm0
0x180011137  movups  [rbp+870h+var_87C], xmm0
0x18001113b  mov     [rbp+870h+var_86C], eax
0x18001113e  movups  [rbp+870h+var_8A0], xmm0
0x180011142  xorps   xmm1, xmm1
0x180011145  movdqu  [rbp+870h+var_8D0], xmm1
0x18001114a  mov     [rbp+870h+var_8D8], rax
0x18001114e  movdqu  [rbp+870h+var_8C0], xmm0
0x180011153  mov     [rbp+870h+var_8B0], rax
0x180011157  or      esi, 0FFFFFFFFh
0x18001115a  mov     [rbp+870h+var_8A8], esi
0x18001115d  mov     [rbp+870h+var_8A4], eax
0x180011160  mov     r8b, cs:byte_1800AA941
0x180011167  mov     dil, 8
0x18001116a  test    dil, r8b
0x18001116d  jz      short loc_18001119B
0x18001116f  mov     rax, [rbx+70h]
0x180011173  mov     [rsp+970h+var_950], rax; void *
0x180011178  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18001117f  lea     r8, [rsp+970h+var_940]; unsigned int *
0x180011184  lea     rdx, aVpnikeconnecti_12; "VPNIKEConnection::ProcessUpdateConnecti"...
0x18001118b  lea     rcx, [rbp+870h+var_8D8]; this
0x18001118f  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x180011194  mov     r8b, cs:byte_1800AA941
0x18001119b  mov     edx, 2
0x1800111a0  cmp     dword ptr [r14+10h], 0
0x1800111a5  jz      loc_1800115F8
0x1800111ab  xorps   xmm6, xmm6
0x1800111ae  xor     eax, eax
0x1800111b0  movups  xmmword ptr [rsp+970h+var_908+0Ah], xmm6
0x1800111b5  movups  xmmword ptr [rsp+970h+var_908+14h], xmm6
0x1800111ba  cmp     dword ptr [r14+10h], 1
0x1800111bf  jnz     loc_18001135C
0x1800111c5  cmp     [r14+14h], eax
0x1800111c9  jz      loc_180011283
0x1800111cf  cmp     word ptr [r14+14h], 0FEA9h
0x1800111d6  jz      loc_180011283
0x1800111dc  cmp     byte ptr [r14+14h], 7Fh
0x1800111e1  jz      loc_180011283
0x1800111e7  test    dil, r8b
0x1800111ea  jz      loc_180011271
0x1800111f0  mov     word ptr [rbp+870h+var_890], ax
0x1800111f4  mov     rax, [rbx+70h]
0x1800111f8  test    rax, rax
0x1800111fb  jz      short loc_180011209
0x1800111fd  cmp     qword ptr [rax+10h], 0
0x180011202  jz      short loc_180011209
0x180011204  mov     edx, [rax+10h]
0x180011207  jmp     short loc_18001120B
0x180011209  mov     edx, esi
0x18001120b  lea     rcx, [rbp+870h+var_890]
0x18001120f  call    ConvertPortNoToString
0x180011214  test    cs:byte_1800AA941, dil
0x18001121b  jz      short loc_18001126C
0x18001121d  mov     rdx, [rbx+70h]
0x180011221  mov     rax, rdx
0x180011224  lea     rcx, [rdx+0A7Eh]
0x18001122b  neg     rax
0x18001122e  sbb     r8, r8
0x180011231  and     r8, rcx
0x180011234  test    rdx, rdx
0x180011237  lea     r9, [rdx+848h]
0x18001123e  jnz     short loc_180011244
0x180011240  lea     r9, [rbp+870h+var_8A0]
0x180011244  lea     rax, [rbp+870h+var_890]
0x180011248  mov     qword ptr [rsp+970h+var_948], rax
0x18001124d  mov     [rsp+970h+var_950], r8
0x180011252  lea     r8, aProcessingMobi; "Processing mobike request using local e"...
0x180011259  lea     rdx, RasVpnIkeParamTraceInfo
0x180011260  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011267  call    McTemplateU0zjzz_EventWriteTransfer
0x18001126c  mov     edx, 2
0x180011271  mov     word ptr [rsp+970h+var_908+8], dx
0x180011276  mov     eax, [r14+14h]
0x18001127a  mov     dword ptr [rsp+970h+var_908+0Ch], eax
0x18001127e  jmp     loc_180011413
0x180011283  mov     dil, 4
0x180011286  test    dil, r8b
0x180011289  jz      short loc_18001130A
0x18001128b  mov     word ptr [rbp+870h+var_890], ax
0x18001128f  mov     rax, [rbx+70h]
0x180011293  test    rax, rax
0x180011296  jz      short loc_1800112A2
0x180011298  cmp     qword ptr [rax+10h], 0
0x18001129d  jz      short loc_1800112A2
0x18001129f  mov     esi, [rax+10h]
0x1800112a2  mov     edx, esi
0x1800112a4  lea     rcx, [rbp+870h+var_890]
0x1800112a8  call    ConvertPortNoToString
0x1800112ad  test    cs:byte_1800AA941, dil
0x1800112b4  jz      short loc_180011305
0x1800112b6  mov     rdx, [rbx+70h]
0x1800112ba  mov     rax, rdx
0x1800112bd  lea     rcx, [rdx+0A7Eh]
0x1800112c4  neg     rax
0x1800112c7  sbb     r8, r8
0x1800112ca  and     r8, rcx
0x1800112cd  test    rdx, rdx
0x1800112d0  lea     r9, [rdx+848h]
0x1800112d7  jnz     short loc_1800112DD
0x1800112d9  lea     r9, [rbp+870h+var_8A0]
0x1800112dd  lea     rax, [rbp+870h+var_890]
0x1800112e1  mov     qword ptr [rsp+970h+var_948], rax
0x1800112e6  mov     [rsp+970h+var_950], r8
0x1800112eb  lea     r8, aInvalidLocalAd_0; "Invalid local address specified."
0x1800112f2  lea     rdx, RasVpnIkeParamTraceError
0x1800112f9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011300  call    McTemplateU0zjzz_EventWriteTransfer
0x180011305  mov     edx, 2
0x18001130a  mov     [rsp+970h+var_940], 57h ; 'W'
0x180011312  mov     rcx, cs:WPP_GLOBAL_Control
0x180011319  lea     rbx, WPP_GLOBAL_Control
0x180011320  cmp     rcx, rbx
0x180011323  jz      loc_1800114FC
0x180011329  test    byte ptr [rcx+1Ch], 1
0x18001132d  jz      loc_1800114CA
0x180011333  cmp     [rcx+19h], dl
0x180011336  jb      loc_1800114CA
0x18001133c  mov     edx, 69h ; 'i'
0x180011341  mov     r9d, 57h ; 'W'
0x180011347  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18001134e  mov     rcx, [rcx+10h]
0x180011352  call    WPP_SF_d
0x180011357  jmp     loc_1800114CA
0x18001135c  movzx   eax, byte ptr [r14+14h]
0x180011361  mov     ecx, 0F0h
0x180011366  and     eax, ecx
0x180011368  jz      loc_18001163A
0x18001136e  cmp     eax, ecx
0x180011370  jz      loc_18001163A
0x180011376  test    dil, r8b
0x180011379  jz      short loc_1800113F9
0x18001137b  xor     eax, eax
0x18001137d  mov     word ptr [rbp+870h+var_890], ax
0x180011381  mov     rax, [rbx+70h]
0x180011385  test    rax, rax
0x180011388  jz      short loc_180011396
0x18001138a  cmp     qword ptr [rax+10h], 0
0x18001138f  jz      short loc_180011396
0x180011391  mov     edx, [rax+10h]
0x180011394  jmp     short loc_180011398
0x180011396  mov     edx, esi
0x180011398  lea     rcx, [rbp+870h+var_890]
0x18001139c  call    ConvertPortNoToString
0x1800113a1  test    cs:byte_1800AA941, dil
0x1800113a8  jz      short loc_1800113F9
0x1800113aa  mov     rdx, [rbx+70h]
0x1800113ae  mov     rax, rdx
0x1800113b1  lea     rcx, [rdx+0A7Eh]
0x1800113b8  neg     rax
0x1800113bb  sbb     r8, r8
0x1800113be  and     r8, rcx
0x1800113c1  test    rdx, rdx
0x1800113c4  lea     r9, [rdx+848h]
0x1800113cb  jnz     short loc_1800113D1
0x1800113cd  lea     r9, [rbp+870h+var_8A0]
0x1800113d1  lea     rax, [rbp+870h+var_890]
0x1800113d5  mov     qword ptr [rsp+970h+var_948], rax
0x1800113da  mov     [rsp+970h+var_950], r8
0x1800113df  lea     r8, aProcessingMobi; "Processing mobike request using local e"...
0x1800113e6  lea     rdx, RasVpnIkeParamTraceInfo
0x1800113ed  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800113f4  call    McTemplateU0zjzz_EventWriteTransfer
0x1800113f9  mov     eax, 17h
0x1800113fe  mov     word ptr [rsp+970h+var_908+8], ax
0x180011403  movups  xmm0, xmmword ptr [r14+14h]
0x180011408  movdqu  xmmword ptr [rsp+970h+var_908+10h], xmm0
0x18001140e  movups  xmm6, xmmword ptr [rsp+970h+var_908+14h]
0x180011413  movups  xmm0, xmmword ptr [rsp+970h+var_908+8]
0x180011418  movaps  xmmword ptr [rsp+970h+var_908+8], xmm0
0x18001141d  movups  xmmword ptr [rsp+970h+var_908+14h], xmm6
0x180011422  mov     rdx, r12
0x180011425  lea     rcx, [rsp+970h+var_908+8]
0x18001142a  call    GetIfIndex
0x18001142f  mov     [rsp+970h+var_940], eax
0x180011433  test    eax, eax
0x180011435  jz      loc_180011536
0x18001143b  mov     dil, 4
0x18001143e  test    cs:byte_1800AA941, dil
0x180011445  jz      short loc_1800114C3
0x180011447  xor     eax, eax
0x180011449  mov     word ptr [rbp+870h+var_890], ax
0x18001144d  mov     rax, [rbx+70h]
0x180011451  test    rax, rax
0x180011454  jz      short loc_180011460
0x180011456  cmp     qword ptr [rax+10h], 0
0x18001145b  jz      short loc_180011460
0x18001145d  mov     esi, [rax+10h]
0x180011460  mov     edx, esi
0x180011462  lea     rcx, [rbp+870h+var_890]
0x180011466  call    ConvertPortNoToString
0x18001146b  test    cs:byte_1800AA941, dil
0x180011472  jz      short loc_1800114C3
0x180011474  mov     rdx, [rbx+70h]
0x180011478  mov     rax, rdx
0x18001147b  lea     rcx, [rdx+0A7Eh]
0x180011482  neg     rax
0x180011485  sbb     r8, r8
0x180011488  and     r8, rcx
0x18001148b  test    rdx, rdx
0x18001148e  lea     r9, [rdx+848h]
0x180011495  jnz     short loc_18001149B
0x180011497  lea     r9, [rbp+870h+var_8A0]
0x18001149b  lea     rax, [rbp+870h+var_890]
0x18001149f  mov     qword ptr [rsp+970h+var_948], rax
0x1800114a4  mov     [rsp+970h+var_950], r8
0x1800114a9  lea     r8, aFailedToRetrie; "Failed to retrieve the interface index "...
0x1800114b0  lea     rdx, RasVpnIkeParamTraceError
0x1800114b7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800114be  call    McTemplateU0zjzz_EventWriteTransfer
0x1800114c3  lea     rbx, WPP_GLOBAL_Control
0x1800114ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800114d1  cmp     rcx, rbx
0x1800114d4  jz      short loc_1800114FC
0x1800114d6  test    byte ptr [rcx+1Ch], 1
0x1800114da  jz      short loc_1800114FC
0x1800114dc  cmp     byte ptr [rcx+19h], 6
0x1800114e0  jb      short loc_1800114FC
0x1800114e2  mov     edx, 6Bh ; 'k'
0x1800114e7  mov     r9d, [rsp+970h+var_940]
0x1800114ec  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x1800114f3  mov     rcx, [rcx+10h]
0x1800114f7  call    WPP_SF_d
0x1800114fc  mov     ebx, [rsp+970h+var_940]
0x180011500  lea     rcx, [rbp+870h+var_8D8]; this
0x180011504  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180011509  mov     eax, ebx
0x18001150b  mov     rcx, [rbp+870h+var_60]
0x180011512  xor     rcx, rsp; StackCookie
0x180011515  call    __security_check_cookie
0x18001151a  movaps  xmm6, [rsp+970h+var_58+8]
0x180011522  add     rsp, 938h
0x180011529  pop     r15
0x18001152b  pop     r14
0x18001152d  pop     r13
0x18001152f  pop     r12
0x180011531  pop     rdi
0x180011532  pop     rsi
0x180011533  pop     rbx
0x180011534  pop     rbp
0x180011535  retn
  ... truncated ...
```
