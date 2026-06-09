# IPv6Helper::ApplyIPv6Settings(void)

- ea: `0x18004e5bc`
- end: `0x18004f403`
- name: `?ApplyIPv6Settings@IPv6Helper@@QEAAKXZ`
- size: `3655`
- prototype: `__int64 __fastcall(IPv6Helper *this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004fdf4`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x180020ba4`
- `0x180039fa8`
- `0x18004e5bc`
- `0x180069644`
- `0x18006cdcc`
- `0x18006db88`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f355`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f373`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f391`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f355`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f373`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f391`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e74a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ebe6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e74a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ebe6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e737`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ebd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f347`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f365`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f383`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e737`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ebd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f347`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f365`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f383`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18004ec17`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18004ec17`
- `DNSAPI!DnsSetConfigDword` at `0x18004ef47`
- `DNSAPI!DnsSetConfigDword` at `0x18004efd0`
- `DNSAPI!DnsSetConfigDword` at `0x18004f078`
- `DNSAPI!DnsSetConfigDword` at `0x18004f101`
- `DNSAPI!DnsSetConfigDword` at `0x18004ef47`
- `DNSAPI!DnsSetConfigDword` at `0x18004efd0`
- `DNSAPI!DnsSetConfigDword` at `0x18004f078`
- `DNSAPI!DnsSetConfigDword` at `0x18004f101`
- `NSI!NsiSetAllParameters` at `0x18004ee75`
- `NSI!NsiSetAllParameters` at `0x18004ee75`

## string_xrefs

- `0x18004f2a7`: `RasUpdateDefaultRouteSettings failed %d`
- `0x18004f320`: `RasUpdateDefaultRouteSettings successfull`
- `0x18004ed8a`: `Update Tcp/Ipv6 settings in registry.`

## pseudocode

```c
__int64 __fastcall IPv6Helper::ApplyIPv6Settings(IPv6Helper *this)
{
  PVOID *v2; // rbx
  _DWORD *v3; // r14
  int v4; // r13d
  unsigned int v5; // esi
  unsigned int v6; // ebx
  char *v7; // r12
  __int64 v8; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int128 *v12; // r9
  const wchar_t *v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int128 *v18; // r9
  _OWORD *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdx
  _OWORD *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rax
  _OWORD *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rax
  _OWORD *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int128 *v33; // r9
  __int64 v34; // rcx
  __int64 v35; // rax
  int cchWideChar; // r14d
  SIZE_T v37; // rbx
  HANDLE v38; // rax
  void *v39; // rax
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int128 *v43; // r9
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rdx
  __int128 *v48; // r9
  __int64 v49; // rax
  unsigned int v50; // ebx
  __int64 v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // rdx
  __int128 *v54; // r9
  char *v55; // rdx
  __int64 v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rdx
  __int128 *v59; // r9
  __int64 v60; // rax
  __int64 v61; // rdx
  __int64 v62; // rdx
  __int128 *v63; // r9
  char *v64; // rdx
  __int64 v65; // rax
  __int64 v66; // rdx
  __int64 v67; // rdx
  __int128 *v68; // r9
  __int64 v69; // rax
  __int64 v70; // rdx
  __int64 v71; // rdx
  __int128 *v72; // r9
  __int64 v73; // rcx
  __int64 v74; // rax
  __int64 v75; // rdx
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rdx
  __int128 *v79; // r9
  STRSAFE_LPWSTR v80; // rbx
  HANDLE v81; // rax
  STRSAFE_LPWSTR v82; // rbx
  HANDLE v83; // rax
  void *v84; // rbx
  HANDLE v85; // rax
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-E0h]
  unsigned int v88; // [rsp+40h] [rbp-C0h] BYREF
  STRSAFE_LPWSTR pszDest[2]; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-A8h]
  __int64 v91; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v92; // [rsp+68h] [rbp-98h]
  __int128 v93; // [rsp+78h] [rbp-88h]
  __int64 v94; // [rsp+88h] [rbp-78h]
  int v95; // [rsp+90h] [rbp-70h]
  int v96; // [rsp+94h] [rbp-6Ch]
  __int128 v97; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v98[24]; // [rsp+B0h] [rbp-50h] BYREF
  int v99; // [rsp+D0h] [rbp-30h]
  int v100; // [rsp+D4h] [rbp-2Ch]
  int v101; // [rsp+D8h] [rbp-28h]
  int v102; // [rsp+DCh] [rbp-24h]
  char v103; // [rsp+E0h] [rbp-20h]
  char v104; // [rsp+E1h] [rbp-1Fh]
  __int16 v105; // [rsp+E2h] [rbp-1Eh]
  int v106; // [rsp+E4h] [rbp-1Ch]
  int v107; // [rsp+E8h] [rbp-18h]
  int v108; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v109; // [rsp+F4h] [rbp-Ch]
  __int128 v110; // [rsp+104h] [rbp+4h]
  int v111; // [rsp+114h] [rbp+14h]
  int v112; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v113[2044]; // [rsp+124h] [rbp+24h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_66f280efc6d63f258d12e6ab97837239_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  *(_OWORD *)pszDest = 0;
  lpMem = 0;
  v88 = 0;
  v3 = (_DWORD *)*((_QWORD *)this + 16);
  v4 = v3[368];
  v112 = 0;
  memset_0(v113, 0, sizeof(v113));
  v108 = 0;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  v97 = 0;
  v92 = 0;
  v91 = 0;
  v93 = 0;
  v94 = 0;
  v5 = -1;
  v95 = -1;
  v96 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v91,
      L"IPv6Helper::ApplyIPv6Settings",
      &v88,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      v3);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != 2 && *((_DWORD *)this + 101) )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
      WPP_SF_d(v2[2], 15, WPP_66f280efc6d63f258d12e6ab97837239_Traceguids, 0);
    v6 = 0;
    goto LABEL_208;
  }
  v7 = (char *)this + 146;
  if ( this != (IPv6Helper *)-146LL )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&v7[2 * v8] );
    ProcessHeap = GetProcessHeap();
    pszDest[0] = (STRSAFE_LPWSTR)HeapAlloc(ProcessHeap, 8u, 2 * v8 + 2);
    if ( !pszDest[0] )
    {
      v88 = 8;
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_197;
      LOWORD(v112) = 0;
      LOWORD(v108) = 0;
      v10 = *((_QWORD *)this + 16);
      if ( v10 && *(_QWORD *)(v10 + 16) )
        v5 = *(_DWORD *)(v10 + 16);
      ConvertPortNoToString(&v108, v5);
      FormatRRASErrorString(&v112, L"Memory Alloc failed and returned %d", v88);
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_197;
      v11 = *((_QWORD *)this + 16);
      LODWORD(v12) = v11 + 2120;
      if ( !v11 )
        v12 = &v97;
      lpWideCharStr = (LPWSTR)((v11 + 2686) & -(__int64)(v11 != 0));
      v13 = (const wchar_t *)&v112;
      goto LABEL_26;
    }
  }
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)&v7[2 * v14] );
  StringCchCopyW(pszDest[0], v14 + 1, (STRSAFE_LPCWSTR)this + 73);
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v112) = 0;
    LOWORD(v108) = 0;
    v15 = *((_QWORD *)this + 16);
    if ( v15 && *(_QWORD *)(v15 + 16) )
      v16 = *(unsigned int *)(v15 + 16);
    else
      v16 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v108, v16);
    FormatRRASErrorString(&v112, L"AdapterName =%ws", pszDest[0]);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v17 = *((_QWORD *)this + 16);
      LODWORD(v18) = v17 + 2120;
      if ( !v17 )
        v18 = &v97;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceInfo,
        (unsigned int)&v112,
        (_DWORD)v18,
        (v17 + 2686) & -(__int64)(v17 != 0),
        (__int64)&v108);
    }
  }
  if ( !IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)this + 2) )
  {
    *(_OWORD *)v98 = *v19;
    v88 = PrependDwIpV6Address(&pszDest[1], 0, v98);
    if ( v88 )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_197;
      LOWORD(v112) = 0;
      LOWORD(v108) = 0;
      v20 = *((_QWORD *)this + 16);
      if ( v20 && *(_QWORD *)(v20 + 16) )
        v5 = *(_DWORD *)(v20 + 16);
      ConvertPortNoToString(&v108, v5);
      FormatRRASErrorString(&v112, L"PrependDwIpV6Address1 =%d", v88);
      goto LABEL_45;
    }
  }
  if ( !IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)this + 1) )
  {
    if ( pszDest[1] )
    {
      v23 = -1;
      do
        ++v23;
      while ( pszDest[1][v23] );
    }
    else
    {
      v23 = 0;
    }
    *(_OWORD *)v98 = *v22;
    v88 = PrependDwIpV6Address(&pszDest[1], v23, v98);
    if ( v88 )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_197;
      LOWORD(v112) = 0;
      LOWORD(v108) = 0;
      v24 = *((_QWORD *)this + 16);
      if ( v24 && *(_QWORD *)(v24 + 16) )
        v5 = *(_DWORD *)(v24 + 16);
      ConvertPortNoToString(&v108, v5);
      FormatRRASErrorString(&v112, L"PrependDwIpV6Address2 =%d", v88);
      goto LABEL_45;
    }
  }
  if ( !IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)((char *)this + 84)) )
  {
    if ( pszDest[1] )
    {
      v26 = -1;
      do
        ++v26;
      while ( pszDest[1][v26] );
    }
    else
    {
      v26 = 0;
    }
    *(_OWORD *)v98 = *v25;
    v88 = PrependDwIpV6Address(&pszDest[1], v26, v98);
    if ( v88 )
      goto LABEL_68;
  }
  if ( !IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)((char *)this + 68)) )
  {
    if ( pszDest[1] )
    {
      v29 = -1;
      do
        ++v29;
      while ( pszDest[1][v29] );
    }
    else
    {
      v29 = 0;
    }
    *(_OWORD *)v98 = *v28;
    v88 = PrependDwIpV6Address(&pszDest[1], v29, v98);
    if ( v88 )
    {
LABEL_68:
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_197;
      v27 = *((_QWORD *)this + 16);
      LOWORD(v108) = 0;
      LOWORD(v112) = 0;
      if ( v27 && *(_QWORD *)(v27 + 16) )
        v5 = *(_DWORD *)(v27 + 16);
      ConvertPortNoToString(&v108, v5);
      FormatRRASErrorString(&v112, L"PrependDwIpV6Address2 remote =%d", v88);
      goto LABEL_45;
    }
  }
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v112) = 0;
    LOWORD(v108) = 0;
    v30 = *((_QWORD *)this + 16);
    if ( v30 && *(_QWORD *)(v30 + 16) )
      v31 = *(unsigned int *)(v30 + 16);
    else
      v31 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v108, v31);
    FormatRRASErrorString(&v112, L"Dns Servers=%ws", pszDest[1]);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v32 = *((_QWORD *)this + 16);
      LODWORD(v33) = v32 + 2120;
      if ( !v32 )
        v33 = &v97;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceInfo,
        (unsigned int)&v112,
        (_DWORD)v33,
        (v32 + 2686) & -(__int64)(v32 != 0),
        (__int64)&v108);
    }
  }
  v34 = *((_QWORD *)this + 16);
  if ( !*(_BYTE *)(v34 + 96) )
    goto LABEL_102;
  v35 = -1;
  do
    ++v35;
  while ( *(_BYTE *)(v34 + v35 + 96) );
  cchWideChar = v35 + 1;
  v37 = 2LL * (unsigned int)(v35 + 1);
  v38 = GetProcessHeap();
  v39 = HeapAlloc(v38, 8u, v37);
  lpMem = v39;
  if ( !v39 )
  {
    v88 = 8;
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_197;
    LOWORD(v112) = 0;
    LOWORD(v108) = 0;
    v46 = *((_QWORD *)this + 16);
    if ( v46 && *(_QWORD *)(v46 + 16) )
      v5 = *(_DWORD *)(v46 + 16);
    ConvertPortNoToString(&v108, v5);
    FormatRRASErrorString(&v112, L"Memory Alloc failed and returned %d", v88);
    goto LABEL_45;
  }
  MultiByteToWideChar(0, 0, (LPCCH)(*((_QWORD *)this + 16) + 96LL), -1, (LPWSTR)v39, cchWideChar);
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v112) = 0;
    LOWORD(v108) = 0;
    v40 = *((_QWORD *)this + 16);
    if ( v40 && *(_QWORD *)(v40 + 16) )
      v41 = *(unsigned int *)(v40 + 16);
    else
      v41 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v108, v41);
    FormatRRASErrorString(&v112, L"Dns Suffux =%ws", lpMem);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v42 = *((_QWORD *)this + 16);
      LODWORD(v43) = v42 + 2120;
      if ( !v42 )
        v43 = &v97;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceInfo,
        (unsigned int)&v112,
        (_DWORD)v43,
        (v42 + 2686) & -(__int64)(v42 != 0),
        (__int64)&v108);
LABEL_102:
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v108) = 0;
        v44 = *((_QWORD *)this + 16);
        if ( v44 && *(_QWORD *)(v44 + 16) )
          v45 = *(unsigned int *)(v44 + 16);
        else
          v45 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v108, v45);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v47 = *((_QWORD *)this + 16);
          LODWORD(v48) = v47 + 2120;
          if ( !v47 )
            v48 = &v97;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"Update Tcp/Ipv6 settings in registry.",
            (_DWORD)v48,
            (v47 + 2686) & -(__int64)(v47 != 0),
            (__int64)&v108);
        }
      }
    }
  }
  v88 = SaveTcpipV6Info(pszDest);
  if ( v88 )
  {
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_197;
    LOWORD(v112) = 0;
    LOWORD(v108) = 0;
    v49 = *((_QWORD *)this + 16);
    if ( v49 && *(_QWORD *)(v49 + 16) )
      v5 = *(_DWORD *)(v49 + 16);
    ConvertPortNoToString(&v108, v5);
    FormatRRASErrorString(&v112, L"SaveTcpipV6Info failed %d", v88);
    goto LABEL_45;
  }
  *((_DWORD *)this + 106) |= 8u;
  if ( *(_QWORD *)this )
  {
    v105 = 0;
    v107 = 0xFFFF;
    v99 = -1;
    v100 = -1;
    v101 = 16;
    v102 = 16;
    v104 = -1;
    v106 = -1;
    *(_QWORD *)v98 = *((_QWORD *)this + 15);
    *(_OWORD *)&v98[8] = *(_OWORD *)this;
    v103 = *((_BYTE *)this + 48);
    v50 = NsiSetAllParameters(1, 1, &NPI_MS_IPV6_MODULEID);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v112) = 0;
      LOWORD(v108) = 0;
      v51 = *((_QWORD *)this + 16);
      if ( v51 && *(_QWORD *)(v51 + 16) )
        v52 = *(unsigned int *)(v51 + 16);
      else
        v52 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v108, v52);
      FormatRRASErrorString(&v112, L"Ipv6 prefix and address plumbig %d", v50);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v53 = *((_QWORD *)this + 16);
        LODWORD(v54) = v53 + 2120;
        if ( !v53 )
          v54 = &v97;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v112,
          (_DWORD)v54,
          (v53 + 2686) & -(__int64)(v53 != 0),
          (__int64)&v108);
      }
    }
  }
  v55 = (char *)this + 146;
  if ( *(_DWORD *)(*((_QWORD *)this + 16) + 88LL) )
  {
    DnsSetConfigDword(65552, v55, 1);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v108) = 0;
      v56 = *((_QWORD *)this + 16);
      if ( v56 && *(_QWORD *)(v56 + 16) )
        v57 = *(unsigned int *)(v56 + 16);
      else
        v57 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v108, v57);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v58 = *((_QWORD *)this + 16);
        LODWORD(v59) = v58 + 2120;
        if ( !v58 )
          v59 = &v97;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"DnsEnableDynamicRegistration",
          (_DWORD)v59,
          (v58 + 2686) & -(__int64)(v58 != 0),
          (__int64)&v108);
      }
    }
  }
  else
  {
    DnsSetConfigDword(65552, v55, 0);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v108) = 0;
      v60 = *((_QWORD *)this + 16);
      if ( v60 && *(_QWORD *)(v60 + 16) )
        v61 = *(unsigned int *)(v60 + 16);
      else
        v61 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v108, v61);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v62 = *((_QWORD *)this + 16);
        LODWORD(v63) = v62 + 2120;
        if ( !v62 )
          v63 = &v97;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"DnsDisableDynamicRegistration",
          (_DWORD)v63,
          (v62 + 2686) & -(__int64)(v62 != 0),
          (__int64)&v108);
      }
    }
  }
  v64 = (char *)this + 146;
  if ( *(_DWORD *)(*((_QWORD *)this + 16) + 92LL) )
  {
    DnsSetConfigDword(10, v64, 1);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v108) = 0;
      v65 = *((_QWORD *)this + 16);
      if ( v65 && *(_QWORD *)(v65 + 16) )
        v66 = *(unsigned int *)(v65 + 16);
      else
        v66 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v108, v66);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v67 = *((_QWORD *)this + 16);
        LODWORD(v68) = v67 + 2120;
        if ( !v67 )
          v68 = &v97;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"DnsEnableAdapterDomainNameRegistration",
          (_DWORD)v68,
          (v67 + 2686) & -(__int64)(v67 != 0),
          (__int64)&v108);
      }
    }
  }
  else
  {
    DnsSetConfigDword(10, v64, 0);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v108) = 0;
      v69 = *((_QWORD *)this + 16);
      if ( v69 && *(_QWORD *)(v69 + 16) )
        v70 = *(unsigned int *)(v69 + 16);
      else
        v70 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v108, v70);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v71 = *((_QWORD *)this + 16);
        LODWORD(v72) = v71 + 2120;
        if ( !v71 )
          v72 = &v97;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"DnsDisableAdapterDomainNameRegistration",
          (_DWORD)v72,
          (v71 + 2686) & -(__int64)(v71 != 0),
          (__int64)&v108);
      }
    }
  }
  if ( v4 == 2 || *((_DWORD *)this + 101) )
    goto LABEL_197;
  v88 = AdjustSelfInterfaceMetrics(0, *((unsigned int *)this + 35), *((_QWORD *)this + 15));
  if ( v88 )
  {
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_197;
    LOWORD(v108) = 0;
    v74 = *((_QWORD *)this + 16);
    if ( v74 && *(_QWORD *)(v74 + 16) )
      v5 = *(_DWORD *)(v74 + 16);
    ConvertPortNoToString(&v108, v5);
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_197;
    v75 = *((_QWORD *)this + 16);
    LODWORD(v12) = v75 + 2120;
    if ( !v75 )
      v12 = &v97;
    lpWideCharStr = (LPWSTR)((v75 + 2686) & -(__int64)(v75 != 0));
    v13 = L"AdjustSelfInterfaceMetrics failed";
LABEL_26:
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasVpnIkeParamTraceError,
      (_DWORD)v13,
      (_DWORD)v12,
      (__int64)lpWideCharStr,
      (__int64)&v108);
    goto LABEL_197;
  }
  if ( *((_BYTE *)this + 144) )
  {
    LOBYTE(v73) = 1;
    v88 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD))xmmword_1800AA9C0)(v73, 0, *((_QWORD *)this + 15));
    if ( !v88 )
    {
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v108) = 0;
        v77 = *((_QWORD *)this + 16);
        if ( v77 && *(_QWORD *)(v77 + 16) )
          v5 = *(_DWORD *)(v77 + 16);
        ConvertPortNoToString(&v108, v5);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v78 = *((_QWORD *)this + 16);
          LODWORD(v79) = v78 + 2120;
          if ( !v78 )
            v79 = &v97;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"RasUpdateDefaultRouteSettings successfull",
            (_DWORD)v79,
            (v78 + 2686) & -(__int64)(v78 != 0),
            (__int64)&v108);
        }
      }
      *((_DWORD *)this + 106) |= 1u;
      goto LABEL_197;
    }
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v112) = 0;
      LOWORD(v108) = 0;
      v76 = *((_QWORD *)this + 16);
      if ( v76 && *(_QWORD *)(v76 + 16) )
        v5 = *(_DWORD *)(v76 + 16);
      ConvertPortNoToString(&v108, v5);
      FormatRRASErrorString(&v112, L"RasUpdateDefaultRouteSettings failed %d", v88);
LABEL_45:
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_197;
      v21 = *((_QWORD *)this + 16);
      LODWORD(v12) = v21 + 2120;
      if ( !v21 )
        v12 = &v97;
      lpWideCharStr = (LPWSTR)((v21 + 2686) & -(__int64)(v21 != 0));
      v13 = (const wchar_t *)&v112;
      goto LABEL_26;
    }
  }
LABEL_197:
  v80 = pszDest[0];
  if ( pszDest[0] )
  {
    v81 = GetProcessHeap();
    HeapFree(v81, 0, v80);
  }
  v82 = pszDest[1];
  if ( pszDest[1] )
  {
    v83 = GetProcessHeap();
    HeapFree(v83, 0, v82);
  }
  v84 = lpMem;
  if ( lpMem )
  {
    v85 = GetProcessHeap();
    HeapFree(v85, 0, v84);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_66f280efc6d63f258d12e6ab97837239_Traceguids, v88);
  }
  v6 = v88;
LABEL_208:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v91);
  return v6;
}

```

## disassembly

```asm
0x18004e5bc  push    rbp
0x18004e5be  push    rbx
0x18004e5bf  push    rsi
0x18004e5c0  push    rdi
0x18004e5c1  push    r12
0x18004e5c3  push    r13
0x18004e5c5  push    r14
0x18004e5c7  push    r15
0x18004e5c9  lea     rbp, [rsp-838h]
0x18004e5d1  sub     rsp, 938h
0x18004e5d8  mov     rax, cs:__security_cookie
0x18004e5df  xor     rax, rsp
0x18004e5e2  mov     [rbp+870h+var_50], rax
0x18004e5e9  mov     rdi, rcx
0x18004e5ec  lea     r12, WPP_GLOBAL_Control
0x18004e5f3  mov     rbx, cs:WPP_GLOBAL_Control
0x18004e5fa  cmp     rbx, r12
0x18004e5fd  jz      short loc_18004E627
0x18004e5ff  test    byte ptr [rbx+1Ch], 1
0x18004e603  jz      short loc_18004E627
0x18004e605  cmp     byte ptr [rbx+19h], 6
0x18004e609  jb      short loc_18004E627
0x18004e60b  mov     edx, 0Eh
0x18004e610  lea     r8, WPP_66f280efc6d63f258d12e6ab97837239_Traceguids
0x18004e617  mov     rcx, [rbx+10h]
0x18004e61b  call    WPP_SF_
0x18004e620  mov     rbx, cs:WPP_GLOBAL_Control
0x18004e627  xorps   xmm0, xmm0
0x18004e62a  movdqu  xmmword ptr [rsp+970h+pszDest], xmm0
0x18004e630  xor     r15d, r15d
0x18004e633  mov     [rsp+970h+lpMem], r15
0x18004e638  mov     [rsp+970h+var_930], r15d
0x18004e63d  mov     r14, [rdi+80h]
0x18004e644  mov     r13d, [r14+5C0h]
0x18004e64b  mov     [rbp+870h+var_850], r15d
0x18004e64f  xor     edx, edx; Val
0x18004e651  mov     r8d, 7FCh; Size
0x18004e657  lea     rcx, [rbp+870h+var_84C]; void *
0x18004e65b  call    memset_0
0x18004e660  mov     [rbp+870h+var_880], r15d
0x18004e664  xorps   xmm0, xmm0
0x18004e667  xor     eax, eax
0x18004e669  movups  [rbp+870h+var_87C], xmm0
0x18004e66d  movups  [rbp+870h+var_86C], xmm0
0x18004e671  mov     [rbp+870h+var_85C], eax
0x18004e674  movups  [rbp+870h+var_8D8], xmm0
0x18004e678  xorps   xmm1, xmm1
0x18004e67b  movdqu  [rsp+970h+var_908], xmm1
0x18004e681  mov     [rsp+970h+var_910], r15
0x18004e686  movdqu  [rsp+970h+var_8F8], xmm0
0x18004e68c  mov     [rbp+870h+var_8E8], r15
0x18004e690  or      esi, 0FFFFFFFFh
0x18004e693  mov     [rbp+870h+var_8E0], esi
0x18004e696  mov     [rbp+870h+var_8DC], r15d
0x18004e69a  test    cs:byte_1800AA941, 8
0x18004e6a1  jz      short loc_18004E6CC
0x18004e6a3  mov     [rsp+970h+lpWideCharStr], r14; void *
0x18004e6a8  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18004e6af  lea     r8, [rsp+970h+var_930]; unsigned int *
0x18004e6b4  lea     rdx, aIpv6helperAppl; "IPv6Helper::ApplyIPv6Settings"
0x18004e6bb  lea     rcx, [rsp+970h+var_910]; this
0x18004e6c0  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18004e6c5  mov     rbx, cs:WPP_GLOBAL_Control
0x18004e6cc  xor     r14d, r14d
0x18004e6cf  cmp     r13d, 2
0x18004e6d3  jz      short loc_18004E70E
0x18004e6d5  cmp     [rdi+194h], r14d
0x18004e6dc  jz      short loc_18004E70E
0x18004e6de  cmp     rbx, r12
0x18004e6e1  jz      short loc_18004E706
0x18004e6e3  test    byte ptr [rbx+1Ch], 1
0x18004e6e7  jz      short loc_18004E706
0x18004e6e9  cmp     byte ptr [rbx+19h], 6
0x18004e6ed  jb      short loc_18004E706
0x18004e6ef  lea     edx, [r14+0Fh]
0x18004e6f3  xor     r9d, r9d
0x18004e6f6  lea     r8, WPP_66f280efc6d63f258d12e6ab97837239_Traceguids
0x18004e6fd  mov     rcx, [rbx+10h]
0x18004e701  call    WPP_SF_d
0x18004e706  mov     ebx, r14d
0x18004e709  jmp     loc_18004F3D4
0x18004e70e  lea     r12, [rdi+92h]
0x18004e715  or      r15, 0FFFFFFFFFFFFFFFFh
0x18004e719  test    r12, r12
0x18004e71c  jz      loc_18004E80F
0x18004e722  mov     rbx, r15
0x18004e725  inc     rbx
0x18004e728  cmp     [r12+rbx*2], r14w
0x18004e72d  jnz     short loc_18004E725
0x18004e72f  lea     rbx, ds:2[rbx*2]
0x18004e737  call    cs:__imp_GetProcessHeap
0x18004e73d  mov     rcx, rax; hHeap
0x18004e740  mov     r8, rbx; dwBytes
0x18004e743  mov     ebx, 8
0x18004e748  mov     edx, ebx; dwFlags
0x18004e74a  call    cs:__imp_HeapAlloc
0x18004e750  mov     [rsp+970h+pszDest], rax
0x18004e755  test    rax, rax
0x18004e758  jnz     loc_18004E814
0x18004e75e  mov     [rsp+970h+var_930], ebx
0x18004e762  test    cs:byte_1800AA941, 4
0x18004e769  jz      loc_18004F33D
0x18004e76f  mov     word ptr [rbp+870h+var_850], r14w
0x18004e774  mov     word ptr [rbp+870h+var_880], r14w
0x18004e779  mov     rax, [rdi+80h]
0x18004e780  test    rax, rax
0x18004e783  jz      short loc_18004E78E
0x18004e785  cmp     [rax+10h], r14
0x18004e789  jz      short loc_18004E78E
0x18004e78b  mov     esi, [rax+10h]
0x18004e78e  mov     edx, esi
0x18004e790  lea     rcx, [rbp+870h+var_880]
0x18004e794  call    ConvertPortNoToString
0x18004e799  mov     r8d, [rsp+970h+var_930]
0x18004e79e  lea     rdx, aMemoryAllocFai; "Memory Alloc failed and returned %d"
0x18004e7a5  lea     rcx, [rbp+870h+var_850]
0x18004e7a9  call    FormatRRASErrorString
0x18004e7ae  test    cs:byte_1800AA941, 4
0x18004e7b5  jz      loc_18004F33D
0x18004e7bb  mov     rdx, [rdi+80h]
0x18004e7c2  mov     rax, rdx
0x18004e7c5  lea     rcx, [rdx+0A7Eh]
0x18004e7cc  neg     rax
0x18004e7cf  sbb     r8, r8
0x18004e7d2  and     r8, rcx
0x18004e7d5  test    rdx, rdx
0x18004e7d8  lea     r9, [rdx+848h]
0x18004e7df  jnz     short loc_18004E7E5
0x18004e7e1  lea     r9, [rbp+870h+var_8D8]
0x18004e7e5  lea     rax, [rbp+870h+var_880]
0x18004e7e9  mov     qword ptr [rsp+970h+cchWideChar], rax
0x18004e7ee  mov     [rsp+970h+lpWideCharStr], r8
0x18004e7f3  lea     r8, [rbp+870h+var_850]
0x18004e7f7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004e7fe  lea     rdx, RasVpnIkeParamTraceError
0x18004e805  call    McTemplateU0zjzz_EventWriteTransfer
0x18004e80a  jmp     loc_18004F33D
0x18004e80f  mov     ebx, 8
0x18004e814  mov     rdx, r15
0x18004e817  inc     rdx
0x18004e81a  cmp     [r12+rdx*2], r14w
0x18004e81f  jnz     short loc_18004E817
0x18004e821  inc     rdx; cchDest
0x18004e824  mov     r8, r12; pszSrc
0x18004e827  mov     rcx, [rsp+970h+pszDest]; pszDest
0x18004e82c  call    StringCchCopyW
0x18004e831  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004e838  test    cs:byte_1800AA941, bl
0x18004e83e  jz      loc_18004E8D8
0x18004e844  mov     word ptr [rbp+870h+var_850], r14w
0x18004e849  mov     word ptr [rbp+870h+var_880], r14w
0x18004e84e  mov     rax, [rdi+80h]
0x18004e855  test    rax, rax
0x18004e858  jz      short loc_18004E865
0x18004e85a  cmp     [rax+10h], r14
0x18004e85e  jz      short loc_18004E865
0x18004e860  mov     edx, [rax+10h]
0x18004e863  jmp     short loc_18004E867
0x18004e865  mov     edx, esi
0x18004e867  lea     rcx, [rbp+870h+var_880]
0x18004e86b  call    ConvertPortNoToString
0x18004e870  mov     r8, [rsp+970h+pszDest]
0x18004e875  lea     rdx, aAdapternameWs_0; "AdapterName =%ws"
0x18004e87c  lea     rcx, [rbp+870h+var_850]
0x18004e880  call    FormatRRASErrorString
0x18004e885  test    cs:byte_1800AA941, bl
0x18004e88b  jz      short loc_18004E8D8
0x18004e88d  mov     rdx, [rdi+80h]
0x18004e894  mov     rax, rdx
0x18004e897  lea     rcx, [rdx+0A7Eh]
0x18004e89e  neg     rax
0x18004e8a1  sbb     r8, r8
0x18004e8a4  and     r8, rcx
0x18004e8a7  test    rdx, rdx
0x18004e8aa  lea     r9, [rdx+848h]
0x18004e8b1  jnz     short loc_18004E8B7
0x18004e8b3  lea     r9, [rbp+870h+var_8D8]
0x18004e8b7  lea     rax, [rbp+870h+var_880]
0x18004e8bb  mov     qword ptr [rsp+970h+cchWideChar], rax
0x18004e8c0  mov     [rsp+970h+lpWideCharStr], r8
0x18004e8c5  lea     r8, [rbp+870h+var_850]
0x18004e8c9  lea     rdx, RasVpnIkeParamTraceInfo
0x18004e8d0  mov     rcx, r15
0x18004e8d3  call    McTemplateU0zjzz_EventWriteTransfer
0x18004e8d8  lea     rcx, [rdi+20h]; a
0x18004e8dc  call    IN6_IS_ADDR_UNSPECIFIED
0x18004e8e1  test    al, al
0x18004e8e3  jnz     loc_18004E9AA
0x18004e8e9  movups  xmm0, xmmword ptr [rcx]
0x18004e8ec  movdqu  [rbp+870h+var_8C0], xmm0
0x18004e8f1  lea     r8, [rbp+870h+var_8C0]
0x18004e8f5  xor     edx, edx
0x18004e8f7  lea     rcx, [rsp+970h+pszDest+8]
0x18004e8fc  call    PrependDwIpV6Address
0x18004e901  mov     [rsp+970h+var_930], eax
0x18004e905  test    eax, eax
0x18004e907  jz      loc_18004E9AA
0x18004e90d  test    cs:byte_1800AA941, 4
0x18004e914  jz      loc_18004F33D
0x18004e91a  mov     word ptr [rbp+870h+var_850], r14w
0x18004e91f  mov     word ptr [rbp+870h+var_880], r14w
0x18004e924  mov     rax, [rdi+80h]
0x18004e92b  test    rax, rax
0x18004e92e  jz      short loc_18004E939
0x18004e930  cmp     [rax+10h], r14
0x18004e934  jz      short loc_18004E939
0x18004e936  mov     esi, [rax+10h]
0x18004e939  mov     edx, esi
0x18004e93b  lea     rcx, [rbp+870h+var_880]
0x18004e93f  call    ConvertPortNoToString
0x18004e944  lea     rdx, aPrependdwipv6a; "PrependDwIpV6Address1 =%d"
0x18004e94b  mov     r8d, [rsp+970h+var_930]
0x18004e950  lea     rcx, [rbp+870h+var_850]
0x18004e954  call    FormatRRASErrorString
0x18004e959  test    cs:byte_1800AA941, 4
0x18004e960  jz      loc_18004F33D
0x18004e966  mov     rdx, [rdi+80h]
0x18004e96d  mov     rax, rdx
0x18004e970  lea     rcx, [rdx+0A7Eh]
0x18004e977  neg     rax
0x18004e97a  sbb     r8, r8
0x18004e97d  and     r8, rcx
0x18004e980  test    rdx, rdx
0x18004e983  lea     r9, [rdx+848h]
0x18004e98a  jnz     short loc_18004E990
0x18004e98c  lea     r9, [rbp+870h+var_8D8]
0x18004e990  lea     rax, [rbp+870h+var_880]
0x18004e994  mov     qword ptr [rsp+970h+cchWideChar], rax
0x18004e999  mov     [rsp+970h+lpWideCharStr], r8
0x18004e99e  lea     r8, [rbp+870h+var_850]
0x18004e9a2  mov     rcx, r15
0x18004e9a5  jmp     loc_18004E7FE
0x18004e9aa  lea     rcx, [rdi+10h]; a
0x18004e9ae  call    IN6_IS_ADDR_UNSPECIFIED
0x18004e9b3  test    al, al
0x18004e9b5  jnz     short loc_18004EA35
0x18004e9b7  mov     rax, [rsp+970h+pszDest+8]
0x18004e9bc  test    rax, rax
0x18004e9bf  jz      short loc_18004E9D1
0x18004e9c1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004e9c5  inc     rdx
0x18004e9c8  cmp     [rax+rdx*2], r14w
0x18004e9cd  jnz     short loc_18004E9C5
0x18004e9cf  jmp     short loc_18004E9D4
0x18004e9d1  mov     rdx, r14
0x18004e9d4  movups  xmm0, xmmword ptr [rcx]
0x18004e9d7  movdqu  [rbp+870h+var_8C0], xmm0
0x18004e9dc  lea     r8, [rbp+870h+var_8C0]
0x18004e9e0  lea     rcx, [rsp+970h+pszDest+8]
0x18004e9e5  call    PrependDwIpV6Address
0x18004e9ea  mov     [rsp+970h+var_930], eax
0x18004e9ee  test    eax, eax
0x18004e9f0  jz      short loc_18004EA35
0x18004e9f2  test    cs:byte_1800AA941, 4
0x18004e9f9  jz      loc_18004F33D
0x18004e9ff  mov     word ptr [rbp+870h+var_850], r14w
0x18004ea04  mov     word ptr [rbp+870h+var_880], r14w
0x18004ea09  mov     rax, [rdi+80h]
0x18004ea10  test    rax, rax
0x18004ea13  jz      short loc_18004EA1E
0x18004ea15  cmp     [rax+10h], r14
0x18004ea19  jz      short loc_18004EA1E
0x18004ea1b  mov     esi, [rax+10h]
0x18004ea1e  mov     edx, esi
0x18004ea20  lea     rcx, [rbp+870h+var_880]
0x18004ea24  call    ConvertPortNoToString
0x18004ea29  lea     rdx, aPrependdwipv6a_1; "PrependDwIpV6Address2 =%d"
0x18004ea30  jmp     loc_18004E94B
0x18004ea35  lea     rcx, [rdi+54h]; a
0x18004ea39  call    IN6_IS_ADDR_UNSPECIFIED
0x18004ea3e  test    al, al
0x18004ea40  jnz     short loc_18004EAC0
0x18004ea42  mov     rax, [rsp+970h+pszDest+8]
0x18004ea47  test    rax, rax
0x18004ea4a  jz      short loc_18004EA5C
0x18004ea4c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004ea50  inc     rdx
0x18004ea53  cmp     [rax+rdx*2], r14w
0x18004ea58  jnz     short loc_18004EA50
0x18004ea5a  jmp     short loc_18004EA5F
0x18004ea5c  mov     rdx, r14
0x18004ea5f  movups  xmm0, xmmword ptr [rcx]
0x18004ea62  movdqu  [rbp+870h+var_8C0], xmm0
0x18004ea67  lea     r8, [rbp+870h+var_8C0]
0x18004ea6b  lea     rcx, [rsp+970h+pszDest+8]
0x18004ea70  call    PrependDwIpV6Address
0x18004ea75  mov     [rsp+970h+var_930], eax
0x18004ea79  test    eax, eax
0x18004ea7b  jz      short loc_18004EAC0
0x18004ea7d  test    cs:byte_1800AA941, 4
0x18004ea84  jz      loc_18004F33D
0x18004ea8a  mov     rax, [rdi+80h]
0x18004ea91  test    rax, rax
0x18004ea94  mov     word ptr [rbp+870h+var_880], r14w
0x18004ea99  mov     word ptr [rbp+870h+var_850], r14w
0x18004ea9e  jz      short loc_18004EAA9
0x18004eaa0  cmp     [rax+10h], r14
0x18004eaa4  jz      short loc_18004EAA9
0x18004eaa6  mov     esi, [rax+10h]
0x18004eaa9  mov     edx, esi
  ... truncated ...
```
