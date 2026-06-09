# IPv4Helper::ApplyIPv4Settings(void)

- ea: `0x18004971c`
- end: `0x18004a4aa`
- name: `?ApplyIPv4Settings@IPv4Helper@@QEAAKXZ`
- size: `3470`
- prototype: `__int64 __fastcall(IPv4Helper *this)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004b840`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18004971c`
- `0x18004ad00`
- `0x180069644`
- `0x1800699e0`
- `0x180069c4c`
- `0x18006bbf8`
- `0x18006bc18`
- `0x18006c42c`
- `0x18006cc78`
- `0x18006cd08`
- `0x18006d494`
- `0x18006f58c`
- `0x180070034`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f39`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180049f59`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180049f59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180049f2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180049f2a`
- `DNSAPI!DnsSetConfigDword` at `0x18004a1e1`
- `DNSAPI!DnsSetConfigDword` at `0x18004a267`
- `DNSAPI!DnsSetConfigDword` at `0x18004a30c`
- `DNSAPI!DnsSetConfigDword` at `0x18004a391`
- `DNSAPI!DnsSetConfigDword` at `0x18004a1e1`
- `DNSAPI!DnsSetConfigDword` at `0x18004a267`
- `DNSAPI!DnsSetConfigDword` at `0x18004a30c`
- `DNSAPI!DnsSetConfigDword` at `0x18004a391`

## string_xrefs

- `0x180049c6e`: `RasUpdateDefaultRouteSettings failed %d`
- `0x180049ce6`: `RasUpdateDefaultRouteSettings successfull`
- `0x18004a101`: `NsiGetCompartmentIdForRoutingDomain failed:%d`

## pseudocode

```c
__int64 __fastcall IPv4Helper::ApplyIPv4Settings(IPv4Helper *this)
{
  PVOID *v2; // rdi
  unsigned int v3; // esi
  _DWORD *v4; // r15
  int v5; // r13d
  unsigned int v6; // r14d
  char v7; // al
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  PVOID v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int128 *v14; // r9
  __int64 v15; // r15
  __int64 v16; // rax
  __int64 v17; // rdx
  __int128 *v18; // r9
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int128 *v22; // r9
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  __int128 *v27; // r9
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int128 *v35; // r9
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 *v46; // r8
  __int64 v47; // rdx
  __int128 *v48; // r9
  __int64 v49; // rdi
  __int64 v50; // rax
  int cchWideChar; // esi
  WCHAR *lpWideCharStr; // rax
  __int64 v53; // rax
  __int64 v54; // rdx
  __int64 v55; // rdx
  __int128 *v56; // r9
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rax
  __int64 v61; // rdx
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rdx
  __int128 *v65; // r9
  char *v66; // rdx
  __int64 v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rdx
  __int128 *v70; // r9
  __int64 v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rdx
  __int128 *v74; // r9
  char *v75; // rdx
  __int64 v76; // rax
  __int64 v77; // rdx
  __int128 *v78; // r9
  __int64 v79; // rax
  __int64 v80; // rdx
  __int128 *v81; // r9
  unsigned int CompartmentIdForRoutingDomain; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v84; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v85; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v86; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v87; // [rsp+48h] [rbp-B8h]
  __int128 v88; // [rsp+58h] [rbp-A8h]
  __int64 v89; // [rsp+68h] [rbp-98h]
  int v90; // [rsp+70h] [rbp-90h]
  int v91; // [rsp+74h] [rbp-8Ch]
  __int128 v92; // [rsp+78h] [rbp-88h] BYREF
  __int128 v93; // [rsp+88h] [rbp-78h] BYREF
  int v94; // [rsp+98h] [rbp-68h] BYREF
  __int128 v95; // [rsp+9Ch] [rbp-64h]
  __int128 v96; // [rsp+ACh] [rbp-54h]
  int v97; // [rsp+BCh] [rbp-44h]
  int v98; // [rsp+C0h] [rbp-40h] BYREF
  char v99[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_9b65cff8e2b438daa92b03f64bab9903_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = 0;
  CompartmentIdForRoutingDomain = 0;
  v85 = 0;
  v4 = (_DWORD *)*((_QWORD *)this + 7);
  v5 = v4[368];
  v93 = 0;
  v84 = 0;
  v98 = 0;
  memset_0(v99, 0, sizeof(v99));
  v94 = 0;
  v95 = 0;
  v96 = 0;
  v97 = 0;
  v92 = 0;
  v87 = 0;
  v86 = 0;
  v88 = 0;
  v89 = 0;
  v6 = -1;
  v90 = -1;
  v91 = 0;
  v7 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v86,
      L"IPv4Helper::ApplyIPv4Settings",
      &CompartmentIdForRoutingDomain,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      v4);
    v3 = CompartmentIdForRoutingDomain;
    v2 = (PVOID *)WPP_GLOBAL_Control;
    v7 = byte_1800AA941;
  }
  v8 = *((_QWORD *)this + 7);
  v93 = *(_OWORD *)(v8 + 2120);
  if ( v5 == 2 || !*((_DWORD *)this + 19) )
  {
    if ( (v7 & 8) != 0 )
    {
      LOWORD(v98) = 0;
      LOWORD(v94) = 0;
      if ( v8 && *(_QWORD *)(v8 + 16) )
        v12 = *(unsigned int *)(v8 + 16);
      else
        v12 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v94, v12);
      FormatRRASErrorString(&v98, L"Calling LoadTcpipInfo for Device=%ws", (char *)this + 80);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v13 = *((_QWORD *)this + 7);
        LODWORD(v14) = v13 + 2120;
        if ( !v13 )
          v14 = &v92;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v98,
          (_DWORD)v14,
          (v13 + 2686) & -(__int64)(v13 != 0),
          (__int64)&v94);
      }
    }
    CompartmentIdForRoutingDomain = LoadTcpipInfo(&v85, (char *)this + 80, 1);
    v15 = v85;
    if ( CompartmentIdForRoutingDomain )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v98) = 0;
        LOWORD(v94) = 0;
        v16 = *((_QWORD *)this + 7);
        if ( v16 && *(_QWORD *)(v16 + 16) )
          v6 = *(_DWORD *)(v16 + 16);
        ConvertPortNoToString(&v94, v6);
        FormatRRASErrorString(&v98, L"LoadTcpipInfo failed %d", CompartmentIdForRoutingDomain);
LABEL_28:
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v17 = *((_QWORD *)this + 7);
          LODWORD(v18) = v17 + 2120;
          if ( !v17 )
            v18 = &v92;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v98,
            (_DWORD)v18,
            (v17 + 2686) & -(__int64)(*((_QWORD *)this + 7) != 0),
            (__int64)&v94);
        }
        goto LABEL_216;
      }
      goto LABEL_216;
    }
    AbcdWszFromIpAddress(*(unsigned int *)this, v85 + 16);
    AbcdWszFromIpAddress(*((unsigned int *)this + 11), v15 + 58);
    *(_DWORD *)(v15 + 4) = *((unsigned __int8 *)this + 73);
    *(_DWORD *)v15 = 1;
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v94) = 0;
      v19 = *((_QWORD *)this + 7);
      if ( v19 && *(_QWORD *)(v19 + 16) )
        v20 = *(unsigned int *)(v19 + 16);
      else
        v20 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v94, v20);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v21 = *((_QWORD *)this + 7);
        LODWORD(v22) = v21 + 2120;
        if ( !v21 )
          v22 = &v92;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"Calling SaveTcpipInfo",
          (_DWORD)v22,
          (v21 + 2686) & -(__int64)(v21 != 0),
          (__int64)&v94);
      }
    }
    CompartmentIdForRoutingDomain = SaveTcpipInfo(v15);
    if ( CompartmentIdForRoutingDomain )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v98) = 0;
        LOWORD(v94) = 0;
        v24 = *((_QWORD *)this + 7);
        if ( v24 && *(_QWORD *)(v24 + 16) )
          v6 = *(_DWORD *)(v24 + 16);
        ConvertPortNoToString(&v94, v6);
        FormatRRASErrorString(&v98, L"SaveTcpipInfo failed %d)", CompartmentIdForRoutingDomain);
        goto LABEL_28;
      }
LABEL_216:
      if ( v15 )
        FreeTcpipInfo(&v85);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
      {
        goto LABEL_223;
      }
      v9 = 20;
      v10 = CompartmentIdForRoutingDomain;
      v11 = (PVOID)*((_QWORD *)WPP_GLOBAL_Control + 2);
LABEL_222:
      WPP_SF_d(v11, v9, WPP_9b65cff8e2b438daa92b03f64bab9903_Traceguids, v10);
LABEL_223:
      v3 = CompartmentIdForRoutingDomain;
      goto LABEL_224;
    }
    *((_DWORD *)this + 90) |= 0x10u;
    if ( v5 != 2 && !*((_DWORD *)this + 19) )
    {
      LOBYTE(v23) = 1;
      CompartmentIdForRoutingDomain = AdjustSelfInterfaceMetrics(
                                        v23,
                                        *((unsigned int *)this + 17),
                                        *((_QWORD *)this + 6));
      if ( CompartmentIdForRoutingDomain )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v94) = 0;
          v25 = *((_QWORD *)this + 7);
          if ( v25 && *(_QWORD *)(v25 + 16) )
            v6 = *(_DWORD *)(v25 + 16);
          ConvertPortNoToString(&v94, v6);
          if ( (byte_1800AA941 & 4) != 0 )
          {
            v26 = *((_QWORD *)this + 7);
            LODWORD(v27) = v26 + 2120;
            if ( !v26 )
              v27 = &v92;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)L"AdjustSelfInterfaceMetrics failed",
              (_DWORD)v27,
              (v26 + 2686) & -(__int64)(v26 != 0),
              (__int64)&v94);
          }
        }
        goto LABEL_216;
      }
      CompartmentIdForRoutingDomain = HelperSetDefaultInterfaceNet(
                                        *(unsigned int *)this,
                                        *((unsigned int *)this + 5),
                                        *((unsigned __int8 *)this + 72),
                                        *((unsigned __int8 *)this + 74),
                                        *((_QWORD *)this + 6));
      if ( CompartmentIdForRoutingDomain )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v98) = 0;
          LOWORD(v94) = 0;
          v30 = *((_QWORD *)this + 7);
          if ( v30 && *(_QWORD *)(v30 + 16) )
            v6 = *(_DWORD *)(v30 + 16);
          ConvertPortNoToString(&v94, v6);
          FormatRRASErrorString(&v98, L"HelperSetDefaultInterfaceNet failed %d", CompartmentIdForRoutingDomain);
          goto LABEL_28;
        }
        goto LABEL_216;
      }
      if ( *((_BYTE *)this + 72) )
      {
        LOBYTE(v28) = 1;
        LOBYTE(v29) = 1;
        CompartmentIdForRoutingDomain = ((__int64 (__fastcall *)(__int64, __int64, _QWORD))xmmword_1800AA9C0)(
                                          v29,
                                          v28,
                                          *((_QWORD *)this + 6));
        if ( CompartmentIdForRoutingDomain )
        {
          if ( (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v98) = 0;
            LOWORD(v94) = 0;
            v31 = *((_QWORD *)this + 7);
            if ( v31 && *(_QWORD *)(v31 + 16) )
              v6 = *(_DWORD *)(v31 + 16);
            ConvertPortNoToString(&v94, v6);
            FormatRRASErrorString(&v98, L"RasUpdateDefaultRouteSettings failed %d", CompartmentIdForRoutingDomain);
            goto LABEL_28;
          }
          goto LABEL_216;
        }
        if ( (byte_1800AA941 & 8) != 0 )
        {
          LOWORD(v94) = 0;
          v32 = *((_QWORD *)this + 7);
          if ( v32 && *(_QWORD *)(v32 + 16) )
            v33 = *(unsigned int *)(v32 + 16);
          else
            v33 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v94, v33);
          if ( (byte_1800AA941 & 8) != 0 )
          {
            v34 = *((_QWORD *)this + 7);
            LODWORD(v35) = v34 + 2120;
            if ( !v34 )
              v35 = &v92;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceInfo,
              (unsigned int)L"RasUpdateDefaultRouteSettings successfull",
              (_DWORD)v35,
              (v34 + 2686) & -(__int64)(v34 != 0),
              (__int64)&v94);
          }
        }
        *((_DWORD *)this + 90) |= 1u;
      }
    }
    *(_DWORD *)v15 = 0;
    if ( *((_DWORD *)this + 4) )
    {
      v36 = *(_QWORD *)(v15 + 104);
      if ( v36 )
      {
        v37 = -1;
        do
          ++v37;
        while ( *(_WORD *)(v36 + 2 * v37) );
      }
      else
      {
        v37 = 0;
      }
      CompartmentIdForRoutingDomain = PrependDwIpAddress(v15 + 104, v37);
      if ( CompartmentIdForRoutingDomain )
        goto LABEL_216;
    }
    if ( *((_DWORD *)this + 3) )
    {
      v38 = *(_QWORD *)(v15 + 104);
      if ( v38 )
      {
        v39 = -1;
        do
          ++v39;
        while ( *(_WORD *)(v38 + 2 * v39) );
      }
      else
      {
        v39 = 0;
      }
      CompartmentIdForRoutingDomain = PrependDwIpAddress(v15 + 104, v39);
      if ( CompartmentIdForRoutingDomain )
        goto LABEL_216;
    }
    if ( *((_DWORD *)this + 9) )
    {
      v40 = *(_QWORD *)(v15 + 104);
      if ( v40 )
      {
        v41 = -1;
        do
          ++v41;
        while ( *(_WORD *)(v40 + 2 * v41) );
      }
      else
      {
        v41 = 0;
      }
      CompartmentIdForRoutingDomain = PrependDwIpAddress(v15 + 104, v41);
      if ( CompartmentIdForRoutingDomain )
        goto LABEL_216;
    }
    if ( *((_DWORD *)this + 8) )
    {
      v42 = *(_QWORD *)(v15 + 104);
      if ( v42 )
      {
        v43 = -1;
        do
          ++v43;
        while ( *(_WORD *)(v42 + 2 * v43) );
      }
      else
      {
        v43 = 0;
      }
      CompartmentIdForRoutingDomain = PrependDwIpAddress(v15 + 104, v43);
      if ( CompartmentIdForRoutingDomain )
        goto LABEL_216;
    }
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v98) = 0;
      LOWORD(v94) = 0;
      v44 = *((_QWORD *)this + 7);
      if ( v44 && *(_QWORD *)(v44 + 16) )
        v45 = *(unsigned int *)(v44 + 16);
      else
        v45 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v94, v45);
      v46 = &qword_180086468;
      if ( *(_QWORD *)(v15 + 104) )
        v46 = *(__int64 **)(v15 + 104);
      FormatRRASErrorString(&v98, L"Dns Servers=%ws", v46);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v47 = *((_QWORD *)this + 7);
        LODWORD(v48) = v47 + 2120;
        if ( !v47 )
          v48 = &v92;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v98,
          (_DWORD)v48,
          (v47 + 2686) & -(__int64)(v47 != 0),
          (__int64)&v94);
      }
    }
    if ( *((_DWORD *)this + 2) )
    {
      CompartmentIdForRoutingDomain = PrependDwIpAddressToMwsz(v15 + 112);
      if ( CompartmentIdForRoutingDomain )
        goto LABEL_216;
    }
    if ( *((_DWORD *)this + 1) )
    {
      CompartmentIdForRoutingDomain = PrependDwIpAddressToMwsz(v15 + 112);
      if ( CompartmentIdForRoutingDomain )
        goto LABEL_216;
    }
    if ( *((_DWORD *)this + 7) )
    {
      CompartmentIdForRoutingDomain = PrependDwIpAddressToMwsz(v15 + 112);
      if ( CompartmentIdForRoutingDomain )
        goto LABEL_216;
    }
    if ( *((_DWORD *)this + 6) )
    {
      CompartmentIdForRoutingDomain = PrependDwIpAddressToMwsz(v15 + 112);
      if ( CompartmentIdForRoutingDomain )
        goto LABEL_216;
    }
    v49 = *((_QWORD *)this + 7);
    if ( *(_BYTE *)(v49 + 96) )
    {
      v50 = -1;
      do
        ++v50;
      while ( *(_BYTE *)(v49 + v50 + 96) );
      cchWideChar = v50 + 1;
      lpWideCharStr = (WCHAR *)LocalAlloc(0x40u, 2LL * (unsigned int)(v50 + 1));
      *(_QWORD *)(v15 + 120) = lpWideCharStr;
      if ( lpWideCharStr )
        MultiByteToWideChar(0xFDE9u, 0, (LPCCH)(v49 + 96), -1, lpWideCharStr, cchWideChar);
      else
        GetLastError();
    }
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v94) = 0;
      v53 = *((_QWORD *)this + 7);
      if ( v53 && *(_QWORD *)(v53 + 16) )
        v54 = *(unsigned int *)(v53 + 16);
      else
        v54 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v94, v54);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v55 = *((_QWORD *)this + 7);
        LODWORD(v56) = v55 + 2120;
        if ( !v55 )
          v56 = &v92;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"SaveTcpipInfo with DNS, etc.",
          (_DWORD)v56,
          (v55 + 2686) & -(__int64)(v55 != 0),
          (__int64)&v94);
      }
    }
    CompartmentIdForRoutingDomain = SaveTcpipInfo(v15);
    if ( CompartmentIdForRoutingDomain )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v98) = 0;
        LOWORD(v94) = 0;
        v57 = *((_QWORD *)this + 7);
        if ( v57 && *(_QWORD *)(v57 + 16) )
          v6 = *(_DWORD *)(v57 + 16);
        ConvertPortNoToString(&v94, v6);
        FormatRRASErrorString(&v98, L"SaveTcpipInfo failed %d", CompartmentIdForRoutingDomain);
        goto LABEL_28;
      }
      goto LABEL_216;
    }
    if ( v5 != 2 && !*((_DWORD *)this + 19) || *(_DWORD *)this )
    {
      CompartmentIdForRoutingDomain = SetIPAddressOnInterface(
                                        *(unsigned int *)this,
                                        *((unsigned int *)this + 11),
                                        (*((_QWORD *)this + 6) >> 24) & 0xFFFFFFLL);
      if ( CompartmentIdForRoutingDomain )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v98) = 0;
          LOWORD(v94) = 0;
          v58 = *((_QWORD *)this + 7);
          if ( v58 && *(_QWORD *)(v58 + 16) )
            v6 = *(_DWORD *)(v58 + 16);
          ConvertPortNoToString(&v94, v6);
          FormatRRASErrorString(&v98, L"SetIPAddressOnInterfacedone failed: %d", CompartmentIdForRoutingDomain);
          goto LABEL_28;
        }
        goto LABEL_216;
      }
      *((_DWORD *)this + 90) |= 8u;
      CompartmentIdForRoutingDomain = NsiGetCompartmentIdForRoutingDomain(&v93, &v84);
      if ( CompartmentIdForRoutingDomain )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v98) = 0;
          LOWORD(v94) = 0;
          v60 = *((_QWORD *)this + 7);
          if ( v60 && *(_QWORD *)(v60 + 16) )
            v61 = *(unsigned int *)(v60 + 16);
          else
            v61 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v94, v61);
          FormatRRASErrorString(&v98, L"NsiGetCompartmentIdForRoutingDomain failed:%d", CompartmentIdForRoutingDomain);
          goto LABEL_172;
        }
        goto LABEL_176;
      }
      CompartmentIdForRoutingDomain = RasTcpAdjustMulticastRouteMetric(*(unsigned int *)this, v59, v84);
      if ( CompartmentIdForRoutingDomain )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v98) = 0;
          LOWORD(v94) = 0;
          v62 = *((_QWORD *)this + 7);
          if ( v62 && *(_QWORD *)(v62 + 16) )
            v63 = *(unsigned int *)(v62 + 16);
          else
            v63 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v94, v63);
          FormatRRASErrorString(&v98, L"RasTcpAdjustMulticastRouteMetric failed:%d", CompartmentIdForRoutingDomain);
LABEL_172:
          if ( (byte_1800AA941 & 4) != 0 )
          {
            v64 = *((_QWORD *)this + 7);
            LODWORD(v65) = v64 + 2120;
            if ( !v64 )
              v65 = &v92;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v98,
              (_DWORD)v65,
              (v64 + 2686) & -(__int64)(*((_QWORD *)this + 7) != 0),
              (__int64)&v94);
          }
        }
LABEL_176:
        CompartmentIdForRoutingDomain = 0;
      }
    }
    v66 = (char *)this + 80;
    if ( *(_DWORD *)(*((_QWORD *)this + 7) + 88LL) )
    {
      DnsSetConfigDword(65552, v66, 1);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v94) = 0;
        v67 = *((_QWORD *)this + 7);
        if ( v67 && *(_QWORD *)(v67 + 16) )
          v68 = *(unsigned int *)(v67 + 16);
        else
          v68 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v94, v68);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v69 = *((_QWORD *)this + 7);
          LODWORD(v70) = v69 + 2120;
          if ( !v69 )
            v70 = &v92;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"DnsEnableDynamicRegistration",
            (_DWORD)v70,
            (v69 + 2686) & -(__int64)(v69 != 0),
            (__int64)&v94);
        }
      }
    }
    else
    {
      DnsSetConfigDword(65552, v66, 0);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v94) = 0;
        v71 = *((_QWORD *)this + 7);
        if ( v71 && *(_QWORD *)(v71 + 16) )
          v72 = *(unsigned int *)(v71 + 16);
        else
          v72 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v94, v72);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v73 = *((_QWORD *)this + 7);
          LODWORD(v74) = v73 + 2120;
          if ( !v73 )
            v74 = &v92;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"DnsDisableDynamicRegistration",
            (_DWORD)v74,
            (v73 + 2686) & -(__int64)(v73 != 0),
            (__int64)&v94);
        }
      }
    }
    v75 = (char *)this + 80;
    if ( *(_DWORD *)(*((_QWORD *)this + 7) + 92LL) )
    {
      DnsSetConfigDword(10, v75, 1);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v94) = 0;
        v76 = *((_QWORD *)this + 7);
        if ( v76 && *(_QWORD *)(v76 + 16) )
          v6 = *(_DWORD *)(v76 + 16);
        ConvertPortNoToString(&v94, v6);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v77 = *((_QWORD *)this + 7);
          LODWORD(v78) = v77 + 2120;
          if ( !v77 )
            v78 = &v92;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"DnsEnableAdapterDomainNameRegistration",
            (_DWORD)v78,
            (v77 + 2686) & -(__int64)(v77 != 0),
            (__int64)&v94);
        }
      }
    }
    else
    {
      DnsSetConfigDword(10, v75, 0);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v94) = 0;
        v79 = *((_QWORD *)this + 7);
        if ( v79 && *(_QWORD *)(v79 + 16) )
          v6 = *(_DWORD *)(v79 + 16);
        ConvertPortNoToString(&v94, v6);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v80 = *((_QWORD *)this + 7);
          LODWORD(v81) = v80 + 2120;
          if ( !v80 )
            v81 = &v92;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"DnsDisableAdapterDomainNameRegistration",
            (_DWORD)v81,
            (v80 + 2686) & -(__int64)(v80 != 0),
            (__int64)&v94);
        }
      }
    }
    if ( v5 != 2 && !*((_DWORD *)this + 19) )
      IPv4Helper::DHCPInform(this);
    goto LABEL_216;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
  {
    v9 = 19;
    v10 = v3;
    v11 = v2[2];
    goto LABEL_222;
  }
LABEL_224:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v86);
  return v3;
}

```

## disassembly

```asm
0x18004971c  push    rbp
0x18004971e  push    rbx
0x18004971f  push    rsi
0x180049720  push    rdi
0x180049721  push    r12
0x180049723  push    r13
0x180049725  push    r14
0x180049727  push    r15
0x180049729  lea     rbp, [rsp-7D8h]
0x180049731  sub     rsp, 8D8h
0x180049738  mov     rax, cs:__security_cookie
0x18004973f  xor     rax, rsp
0x180049742  mov     [rbp+810h+var_50], rax
0x180049749  mov     rbx, rcx
0x18004974c  lea     rax, WPP_GLOBAL_Control
0x180049753  mov     rdi, cs:WPP_GLOBAL_Control
0x18004975a  cmp     rdi, rax
0x18004975d  jz      short loc_180049787
0x18004975f  test    byte ptr [rdi+1Ch], 1
0x180049763  jz      short loc_180049787
0x180049765  cmp     byte ptr [rdi+19h], 6
0x180049769  jb      short loc_180049787
0x18004976b  mov     edx, 12h
0x180049770  lea     r8, WPP_9b65cff8e2b438daa92b03f64bab9903_Traceguids
0x180049777  mov     rcx, [rdi+10h]
0x18004977b  call    WPP_SF_
0x180049780  mov     rdi, cs:WPP_GLOBAL_Control
0x180049787  xor     r12d, r12d
0x18004978a  mov     esi, r12d
0x18004978d  mov     [rsp+910h+var_8E0], r12d
0x180049792  mov     [rsp+910h+var_8D8], r12
0x180049797  mov     r15, [rbx+38h]
0x18004979b  mov     r13d, [r15+5C0h]
0x1800497a2  xorps   xmm0, xmm0
0x1800497a5  movups  [rbp+810h+var_888], xmm0
0x1800497a9  mov     [rsp+910h+var_8DC], r12d
0x1800497ae  mov     [rbp+810h+var_850], r12d
0x1800497b2  xor     edx, edx; Val
0x1800497b4  mov     r8d, 7FCh; Size
0x1800497ba  lea     rcx, [rbp+810h+var_84C]; void *
0x1800497be  call    memset_0
0x1800497c3  mov     [rbp+810h+var_878], r12d
0x1800497c7  xorps   xmm0, xmm0
0x1800497ca  xor     eax, eax
0x1800497cc  movups  [rbp+810h+var_874], xmm0
0x1800497d0  movups  [rbp+810h+var_864], xmm0
0x1800497d4  mov     [rbp+810h+var_854], eax
0x1800497d7  movups  [rsp+910h+var_898], xmm0
0x1800497dc  xorps   xmm1, xmm1
0x1800497df  movdqu  [rsp+910h+var_8C8], xmm1
0x1800497e5  mov     [rsp+910h+var_8D0], r12
0x1800497ea  movdqu  [rsp+910h+var_8B8], xmm0
0x1800497f0  mov     [rsp+910h+var_8A8], r12
0x1800497f5  or      r14d, 0FFFFFFFFh
0x1800497f9  mov     [rsp+910h+var_8A0], r14d
0x1800497fe  mov     [rsp+910h+var_89C], r12d
0x180049803  mov     al, cs:byte_1800AA941
0x180049809  test    al, 8
0x18004980b  jz      short loc_180049840
0x18004980d  mov     [rsp+910h+lpWideCharStr], r15; void *
0x180049812  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180049819  lea     r8, [rsp+910h+var_8E0]; unsigned int *
0x18004981e  lea     rdx, aIpv4helperAppl; "IPv4Helper::ApplyIPv4Settings"
0x180049825  lea     rcx, [rsp+910h+var_8D0]; this
0x18004982a  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18004982f  mov     esi, [rsp+910h+var_8E0]
0x180049833  mov     rdi, cs:WPP_GLOBAL_Control
0x18004983a  mov     al, cs:byte_1800AA941
0x180049840  mov     rcx, [rbx+38h]
0x180049844  movups  xmm0, xmmword ptr [rcx+848h]
0x18004984b  movdqu  [rbp+810h+var_888], xmm0
0x180049850  cmp     r13d, 2
0x180049854  jz      short loc_180049891
0x180049856  cmp     [rbx+4Ch], r12d
0x18004985a  jz      short loc_180049891
0x18004985c  lea     rax, WPP_GLOBAL_Control
0x180049863  cmp     rdi, rax
0x180049866  jz      loc_18004A47B
0x18004986c  test    byte ptr [rdi+1Ch], 1
0x180049870  jz      loc_18004A47B
0x180049876  cmp     byte ptr [rdi+19h], 6
0x18004987a  jb      loc_18004A47B
0x180049880  mov     edx, 13h
0x180049885  mov     r9d, esi
0x180049888  mov     rcx, [rdi+10h]
0x18004988c  jmp     loc_18004A46B
0x180049891  mov     edi, 8
0x180049896  xor     esi, esi
0x180049898  test    dil, al
0x18004989b  jz      loc_18004992F
0x1800498a1  mov     word ptr [rbp+810h+var_850], si
0x1800498a5  mov     word ptr [rbp+810h+var_878], si
0x1800498a9  test    rcx, rcx
0x1800498ac  jz      short loc_1800498B9
0x1800498ae  cmp     [rcx+10h], rsi
0x1800498b2  jz      short loc_1800498B9
0x1800498b4  mov     edx, [rcx+10h]
0x1800498b7  jmp     short loc_1800498BC
0x1800498b9  mov     edx, r14d
0x1800498bc  lea     rcx, [rbp+810h+var_878]
0x1800498c0  call    ConvertPortNoToString
0x1800498c5  lea     r8, [rbx+50h]
0x1800498c9  lea     rdx, aCallingLoadtcp; "Calling LoadTcpipInfo for Device=%ws"
0x1800498d0  lea     rcx, [rbp+810h+var_850]
0x1800498d4  call    FormatRRASErrorString
0x1800498d9  test    cs:byte_1800AA941, dil
0x1800498e0  jz      short loc_18004992F
0x1800498e2  mov     rdx, [rbx+38h]
0x1800498e6  mov     rax, rdx
0x1800498e9  lea     rcx, [rdx+0A7Eh]
0x1800498f0  neg     rax
0x1800498f3  sbb     r8, r8
0x1800498f6  and     r8, rcx
0x1800498f9  test    rdx, rdx
0x1800498fc  lea     r9, [rdx+848h]
0x180049903  jnz     short loc_18004990A
0x180049905  lea     r9, [rsp+910h+var_898]
0x18004990a  lea     rax, [rbp+810h+var_878]
0x18004990e  mov     qword ptr [rsp+910h+cchWideChar], rax
0x180049913  mov     [rsp+910h+lpWideCharStr], r8
0x180049918  lea     r8, [rbp+810h+var_850]
0x18004991c  lea     rdx, RasVpnIkeParamTraceInfo
0x180049923  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004992a  call    McTemplateU0zjzz_EventWriteTransfer
0x18004992f  lea     r12, [rbx+50h]
0x180049933  mov     r8d, 1
0x180049939  mov     rdx, r12
0x18004993c  lea     rcx, [rsp+910h+var_8D8]
0x180049941  call    LoadTcpipInfo
0x180049946  mov     [rsp+910h+var_8E0], eax
0x18004994a  mov     r15, [rsp+910h+var_8D8]
0x18004994f  test    eax, eax
0x180049951  jz      loc_1800499FF
0x180049957  test    cs:byte_1800AA941, 4
0x18004995e  jz      loc_18004A42F
0x180049964  mov     word ptr [rbp+810h+var_850], si
0x180049968  mov     word ptr [rbp+810h+var_878], si
0x18004996c  mov     rax, [rbx+38h]
0x180049970  test    rax, rax
0x180049973  jz      short loc_18004997F
0x180049975  cmp     [rax+10h], rsi
0x180049979  jz      short loc_18004997F
0x18004997b  mov     r14d, [rax+10h]
0x18004997f  mov     edx, r14d
0x180049982  lea     rcx, [rbp+810h+var_878]
0x180049986  call    ConvertPortNoToString
0x18004998b  lea     rdx, aLoadtcpipinfoF; "LoadTcpipInfo failed %d"
0x180049992  mov     r8d, [rsp+910h+var_8E0]
0x180049997  lea     rcx, [rbp+810h+var_850]
0x18004999b  call    FormatRRASErrorString
0x1800499a0  test    cs:byte_1800AA941, 4
0x1800499a7  jz      loc_18004A42F
0x1800499ad  mov     rdx, [rbx+38h]
0x1800499b1  mov     rax, rdx
0x1800499b4  neg     rax
0x1800499b7  lea     rcx, [rdx+0A7Eh]
0x1800499be  sbb     r8, r8
0x1800499c1  and     r8, rcx
0x1800499c4  lea     r9, [rdx+848h]
0x1800499cb  test    rdx, rdx
0x1800499ce  jnz     short loc_1800499D5
0x1800499d0  lea     r9, [rsp+910h+var_898]
0x1800499d5  lea     rax, [rbp+810h+var_878]
0x1800499d9  mov     qword ptr [rsp+910h+cchWideChar], rax
0x1800499de  mov     [rsp+910h+lpWideCharStr], r8
0x1800499e3  lea     r8, [rbp+810h+var_850]
0x1800499e7  lea     rdx, RasVpnIkeParamTraceError
0x1800499ee  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800499f5  call    McTemplateU0zjzz_EventWriteTransfer
0x1800499fa  jmp     loc_18004A42F
0x1800499ff  lea     rdx, [r15+10h]
0x180049a03  mov     ecx, [rbx]
0x180049a05  call    AbcdWszFromIpAddress
0x180049a0a  lea     rdx, [r15+3Ah]
0x180049a0e  mov     ecx, [rbx+2Ch]
0x180049a11  call    AbcdWszFromIpAddress
0x180049a16  movzx   eax, byte ptr [rbx+49h]
0x180049a1a  mov     [r15+4], eax
0x180049a1e  mov     dword ptr [r15], 1
0x180049a25  test    cs:byte_1800AA941, dil
0x180049a2c  jz      short loc_180049AAB
0x180049a2e  mov     word ptr [rbp+810h+var_878], si
0x180049a32  mov     rax, [rbx+38h]
0x180049a36  test    rax, rax
0x180049a39  jz      short loc_180049A46
0x180049a3b  cmp     [rax+10h], rsi
0x180049a3f  jz      short loc_180049A46
0x180049a41  mov     edx, [rax+10h]
0x180049a44  jmp     short loc_180049A49
0x180049a46  mov     edx, r14d
0x180049a49  lea     rcx, [rbp+810h+var_878]
0x180049a4d  call    ConvertPortNoToString
0x180049a52  test    cs:byte_1800AA941, dil
0x180049a59  jz      short loc_180049AAB
0x180049a5b  mov     rdx, [rbx+38h]
0x180049a5f  mov     rax, rdx
0x180049a62  lea     rcx, [rdx+0A7Eh]
0x180049a69  neg     rax
0x180049a6c  sbb     r8, r8
0x180049a6f  and     r8, rcx
0x180049a72  test    rdx, rdx
0x180049a75  lea     r9, [rdx+848h]
0x180049a7c  jnz     short loc_180049A83
0x180049a7e  lea     r9, [rsp+910h+var_898]
0x180049a83  lea     rax, [rbp+810h+var_878]
0x180049a87  mov     qword ptr [rsp+910h+cchWideChar], rax
0x180049a8c  mov     [rsp+910h+lpWideCharStr], r8
0x180049a91  lea     r8, aCallingSavetcp; "Calling SaveTcpipInfo"
0x180049a98  lea     rdx, RasVpnIkeParamTraceInfo
0x180049a9f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180049aa6  call    McTemplateU0zjzz_EventWriteTransfer
0x180049aab  mov     rcx, r15
0x180049aae  call    SaveTcpipInfo
0x180049ab3  mov     [rsp+910h+var_8E0], eax
0x180049ab7  test    eax, eax
0x180049ab9  jz      short loc_180049AFB
0x180049abb  test    cs:byte_1800AA941, 4
0x180049ac2  jz      loc_18004A42F
0x180049ac8  mov     word ptr [rbp+810h+var_850], si
0x180049acc  mov     word ptr [rbp+810h+var_878], si
0x180049ad0  mov     rax, [rbx+38h]
0x180049ad4  test    rax, rax
0x180049ad7  jz      short loc_180049AE3
0x180049ad9  cmp     [rax+10h], rsi
0x180049add  jz      short loc_180049AE3
0x180049adf  mov     r14d, [rax+10h]
0x180049ae3  mov     edx, r14d
0x180049ae6  lea     rcx, [rbp+810h+var_878]
0x180049aea  call    ConvertPortNoToString
0x180049aef  lea     rdx, aSavetcpipinfoF_1; "SaveTcpipInfo failed %d)"
0x180049af6  jmp     loc_180049992
0x180049afb  or      dword ptr [rbx+168h], 10h
0x180049b02  cmp     r13d, 2
0x180049b06  jz      loc_180049D07
0x180049b0c  cmp     [rbx+4Ch], esi
0x180049b0f  jnz     loc_180049D07
0x180049b15  mov     r8, [rbx+30h]
0x180049b19  mov     edx, [rbx+44h]
0x180049b1c  mov     cl, 1
0x180049b1e  call    AdjustSelfInterfaceMetrics
0x180049b23  mov     [rsp+910h+var_8E0], eax
0x180049b27  test    eax, eax
0x180049b29  jz      short loc_180049BAA
0x180049b2b  test    cs:byte_1800AA941, 4
0x180049b32  jz      loc_18004A42F
0x180049b38  mov     word ptr [rbp+810h+var_878], si
0x180049b3c  mov     rax, [rbx+38h]
0x180049b40  test    rax, rax
0x180049b43  jz      short loc_180049B4F
0x180049b45  cmp     [rax+10h], rsi
0x180049b49  jz      short loc_180049B4F
0x180049b4b  mov     r14d, [rax+10h]
0x180049b4f  mov     edx, r14d
0x180049b52  lea     rcx, [rbp+810h+var_878]
0x180049b56  call    ConvertPortNoToString
0x180049b5b  test    cs:byte_1800AA941, 4
0x180049b62  jz      loc_18004A42F
0x180049b68  mov     rdx, [rbx+38h]
0x180049b6c  mov     rax, rdx
0x180049b6f  lea     rcx, [rdx+0A7Eh]
0x180049b76  neg     rax
0x180049b79  sbb     r8, r8
0x180049b7c  and     r8, rcx
0x180049b7f  test    rdx, rdx
0x180049b82  lea     r9, [rdx+848h]
0x180049b89  jnz     short loc_180049B90
0x180049b8b  lea     r9, [rsp+910h+var_898]
0x180049b90  lea     rax, [rbp+810h+var_878]
0x180049b94  mov     qword ptr [rsp+910h+cchWideChar], rax
0x180049b99  mov     [rsp+910h+lpWideCharStr], r8
0x180049b9e  lea     r8, aAdjustselfinte; "AdjustSelfInterfaceMetrics failed"
0x180049ba5  jmp     loc_1800499E7
0x180049baa  movzx   r9d, byte ptr [rbx+4Ah]
0x180049baf  movzx   r8d, byte ptr [rbx+48h]
0x180049bb4  mov     rax, [rbx+30h]
0x180049bb8  mov     [rsp+910h+lpWideCharStr], rax
0x180049bbd  mov     edx, [rbx+14h]
0x180049bc0  mov     ecx, [rbx]
0x180049bc2  call    HelperSetDefaultInterfaceNet
0x180049bc7  mov     [rsp+910h+var_8E0], eax
0x180049bcb  test    eax, eax
0x180049bcd  jz      short loc_180049C0F
0x180049bcf  test    cs:byte_1800AA941, 4
0x180049bd6  jz      loc_18004A42F
0x180049bdc  mov     word ptr [rbp+810h+var_850], si
0x180049be0  mov     word ptr [rbp+810h+var_878], si
0x180049be4  mov     rax, [rbx+38h]
0x180049be8  test    rax, rax
0x180049beb  jz      short loc_180049BF7
0x180049bed  cmp     [rax+10h], rsi
0x180049bf1  jz      short loc_180049BF7
0x180049bf3  mov     r14d, [rax+10h]
0x180049bf7  mov     edx, r14d
0x180049bfa  lea     rcx, [rbp+810h+var_878]
0x180049bfe  call    ConvertPortNoToString
0x180049c03  lea     rdx, aHelpersetdefau; "HelperSetDefaultInterfaceNet failed %d"
0x180049c0a  jmp     loc_180049992
0x180049c0f  cmp     [rbx+48h], sil
0x180049c13  jz      loc_180049D07
0x180049c19  mov     r9b, 1
  ... truncated ...
```
