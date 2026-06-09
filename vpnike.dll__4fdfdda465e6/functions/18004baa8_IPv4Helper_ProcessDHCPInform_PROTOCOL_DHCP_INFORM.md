# IPv4Helper::ProcessDHCPInform(_PROTOCOL_DHCP_INFORM *)

- ea: `0x18004baa8`
- end: `0x18004c482`
- name: `?ProcessDHCPInform@IPv4Helper@@QEAAKPEAU_PROTOCOL_DHCP_INFORM@@@Z`
- size: `2522`
- prototype: `__int64 __fastcall(IPv4Helper *this, struct _PROTOCOL_DHCP_INFORM *)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180002e70`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18004baa8`
- `0x18006bc18`
- `0x18006c42c`
- `0x18006cc78`
- `0x18006cd08`
- `0x18006d494`
- `0x180070498`
- `0x180070c2c`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c12a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c12a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c194`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18004c18a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18004c18a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004c11b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004c11b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c10b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c3f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c3fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c409`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c10b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c3f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c3fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c409`

## pseudocode

```c
__int64 __fastcall IPv4Helper::ProcessDHCPInform(IPv4Helper *this, struct _PROTOCOL_DHCP_INFORM *a2)
{
  unsigned int v4; // edi
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int128 *v8; // r9
  __int64 v9; // rax
  __int64 v10; // rdx
  __int128 *v11; // r9
  __int64 *v12; // r15
  __int64 v13; // r14
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // r8
  __int64 v17; // rdx
  __int128 *v18; // r9
  int v19; // esi
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rax
  char v23; // al
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int128 *v27; // r9
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  unsigned int cchWideChar; // esi
  __int64 v33; // rax
  __int64 v34; // rdx
  __int128 *v35; // r9
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int128 *v39; // r9
  WCHAR *v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rdx
  __int128 *v46; // r9
  int v47; // r9d
  __int64 v48; // rax
  unsigned int v49; // esi
  int v50; // r8d
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rdx
  __int128 *v54; // r9
  unsigned int v55; // ebx
  int lpWideCharStr; // [rsp+20h] [rbp-E0h]
  unsigned int LastError; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v59; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v60; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v61; // [rsp+48h] [rbp-B8h]
  __int128 v62; // [rsp+58h] [rbp-A8h]
  __int64 v63; // [rsp+68h] [rbp-98h]
  int v64; // [rsp+70h] [rbp-90h]
  int v65; // [rsp+74h] [rbp-8Ch]
  __int128 v66; // [rsp+78h] [rbp-88h] BYREF
  int v67; // [rsp+88h] [rbp-78h] BYREF
  __int128 v68; // [rsp+8Ch] [rbp-74h]
  __int128 v69; // [rsp+9Ch] [rbp-64h]
  int v70; // [rsp+ACh] [rbp-54h]
  int v71; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v72[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_9b65cff8e2b438daa92b03f64bab9903_Traceguids);
  }
  v59 = 0;
  LastError = 0;
  v71 = 0;
  memset_0(v72, 0, sizeof(v72));
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v66 = 0;
  v61 = 0;
  v60 = 0;
  v62 = 0;
  v63 = 0;
  v4 = -1;
  v64 = -1;
  v65 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v60,
      L"IPv4Helper::ProcessDHCPInform",
      &LastError,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      *((void **)this + 7));
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v71) = 0;
      LOWORD(v67) = 0;
      v5 = *((_QWORD *)this + 7);
      if ( v5 && *(_QWORD *)(v5 + 16) )
        v6 = *(unsigned int *)(v5 + 16);
      else
        v6 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v67, v6);
      FormatRRASErrorString(&v71, L"DHCPInform returned Device=%ws)", *(_QWORD *)a2);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v7 = *((_QWORD *)this + 7);
        LODWORD(v8) = v7 + 2120;
        if ( !v7 )
          v8 = &v66;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v71,
          (_DWORD)v8,
          (v7 + 2686) & -(__int64)(v7 != 0),
          (__int64)&v67);
      }
    }
  }
  LastError = LoadTcpipInfo(&v59, *(_QWORD *)a2, 0);
  if ( !LastError )
  {
    v12 = qword_18007E870;
    v13 = v59;
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v71) = 0;
      LOWORD(v67) = 0;
      v14 = *((_QWORD *)this + 7);
      if ( v14 && *(_QWORD *)(v14 + 16) )
        v15 = *(unsigned int *)(v14 + 16);
      else
        v15 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v67, v15);
      v16 = qword_18007E870;
      if ( *(_QWORD *)(v13 + 104) )
        v16 = *(__int64 **)(v13 + 104);
      FormatRRASErrorString(&v71, L"Old Dns=%ws", v16);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v17 = *((_QWORD *)this + 7);
        LODWORD(v18) = v17 + 2120;
        if ( !v17 )
          v18 = &v66;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v71,
          (_DWORD)v18,
          (v17 + 2686) & -(__int64)(v17 != 0),
          (__int64)&v67);
      }
    }
    v19 = *((_DWORD *)a2 + 2);
    while ( v19 )
    {
      --v19;
      v20 = *(_QWORD *)(v13 + 104);
      if ( v20 )
      {
        v21 = -1;
        do
          ++v21;
        while ( *(_WORD *)(v20 + 2 * v21) );
      }
      else
      {
        v21 = 0;
      }
      LastError = PrependDwIpAddress(v13 + 104, v21);
      if ( LastError )
      {
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_140;
        LOWORD(v71) = 0;
        LOWORD(v67) = 0;
        v22 = *((_QWORD *)this + 7);
        if ( v22 && *(_QWORD *)(v22 + 16) )
          v4 = *(_DWORD *)(v22 + 16);
        ConvertPortNoToString(&v67, v4);
        FormatRRASErrorString(&v71, L"DNS PrependDwIpAddress failed: %d", LastError);
        goto LABEL_21;
      }
    }
    v23 = byte_1800AA941;
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v71) = 0;
      LOWORD(v67) = 0;
      v24 = *((_QWORD *)this + 7);
      if ( v24 && *(_QWORD *)(v24 + 16) )
        v25 = *(unsigned int *)(v24 + 16);
      else
        v25 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v67, v25);
      if ( *(_QWORD *)(v13 + 104) )
        v12 = *(__int64 **)(v13 + 104);
      FormatRRASErrorString(&v71, L"ProcesDHCPInform: New Dns=%ws", v12);
      v23 = byte_1800AA941;
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v26 = *((_QWORD *)this + 7);
        LODWORD(v27) = v26 + 2120;
        if ( !v26 )
          v27 = &v66;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v71,
          (_DWORD)v27,
          (v26 + 2686) & -(__int64)(v26 != 0),
          (__int64)&v67);
        v23 = byte_1800AA941;
      }
    }
    if ( *((_DWORD *)a2 + 6) )
    {
      if ( *((_DWORD *)a2 + 7) )
      {
        LastError = PrependDwIpAddressToMwsz(v13 + 112);
        if ( LastError )
        {
          if ( (byte_1800AA941 & 4) == 0 )
            goto LABEL_140;
          LOWORD(v71) = 0;
          LOWORD(v67) = 0;
          v28 = *((_QWORD *)this + 7);
          if ( v28 && *(_QWORD *)(v28 + 16) )
            v4 = *(_DWORD *)(v28 + 16);
          ConvertPortNoToString(&v67, v4);
          FormatRRASErrorString(&v71, L"WINS2 PrependDwIpAddressToMwsz failed: %d", LastError);
          goto LABEL_21;
        }
      }
      LastError = PrependDwIpAddressToMwsz(v13 + 112);
      if ( LastError )
      {
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_140;
        LOWORD(v71) = 0;
        LOWORD(v67) = 0;
        v29 = *((_QWORD *)this + 7);
        if ( v29 && *(_QWORD *)(v29 + 16) )
          v4 = *(_DWORD *)(v29 + 16);
        ConvertPortNoToString(&v67, v4);
        FormatRRASErrorString(&v71, L"WINS1 PrependDwIpAddressToMwsz failed: %d", LastError);
        goto LABEL_21;
      }
      v23 = byte_1800AA941;
    }
    v30 = *((_QWORD *)a2 + 5);
    if ( v30 )
    {
      v31 = -1;
      do
        ++v31;
      while ( *(_BYTE *)(v30 + v31) );
      cchWideChar = v31 + 1;
      if ( (unsigned int)(v31 + 1) > 0x100 )
      {
        LastError = 87;
        if ( (v23 & 4) != 0 )
        {
          LOWORD(v67) = 0;
          v33 = *((_QWORD *)this + 7);
          if ( v33 && *(_QWORD *)(v33 + 16) )
            v4 = *(_DWORD *)(v33 + 16);
          ConvertPortNoToString(&v67, v4);
          if ( (byte_1800AA941 & 4) != 0 )
          {
            v34 = *((_QWORD *)this + 7);
            LODWORD(v35) = v34 + 2120;
            if ( !v34 )
              v35 = &v66;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)L"DomainNameSize from DHCP inform is greater than 255",
              (_DWORD)v35,
              (v34 + 2686) & -(__int64)(v34 != 0),
              (__int64)&v67);
          }
        }
        goto LABEL_140;
      }
      if ( (v23 & 8) != 0 )
      {
        LOWORD(v71) = 0;
        LOWORD(v67) = 0;
        v36 = *((_QWORD *)this + 7);
        if ( v36 && *(_QWORD *)(v36 + 16) )
          v37 = *(unsigned int *)(v36 + 16);
        else
          v37 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v67, v37);
        FormatRRASErrorString(&v71, L"DomainName %S", *((_QWORD *)a2 + 5));
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v38 = *((_QWORD *)this + 7);
          LODWORD(v39) = v38 + 2120;
          if ( !v38 )
            v39 = &v66;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)&v71,
            (_DWORD)v39,
            (v38 + 2686) & -(__int64)(v38 != 0),
            (__int64)&v67);
        }
      }
      LocalFree(*(HLOCAL *)(v13 + 120));
      v40 = (WCHAR *)LocalAlloc(0x40u, 2LL * cchWideChar);
      *(_QWORD *)(v13 + 120) = v40;
      if ( !v40 )
      {
        LastError = GetLastError();
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_140;
        LOWORD(v71) = 0;
        LOWORD(v67) = 0;
        v41 = *((_QWORD *)this + 7);
        if ( v41 && *(_QWORD *)(v41 + 16) )
          v4 = *(_DWORD *)(v41 + 16);
        ConvertPortNoToString(&v67, v4);
        FormatRRASErrorString(&v71, L"LocalAlloc failed %d", LastError);
        goto LABEL_21;
      }
      if ( !MultiByteToWideChar(0, 0, *((LPCCH *)a2 + 5), -1, v40, cchWideChar) )
      {
        LastError = GetLastError();
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_140;
        LOWORD(v71) = 0;
        LOWORD(v67) = 0;
        v42 = *((_QWORD *)this + 7);
        if ( v42 && *(_QWORD *)(v42 + 16) )
          v4 = *(_DWORD *)(v42 + 16);
        ConvertPortNoToString(&v67, v4);
        FormatRRASErrorString(&v71, L"Error %d converting domain name %S", LastError, *((_QWORD *)a2 + 5));
        goto LABEL_21;
      }
    }
    *(_DWORD *)(v13 + 4) = *((unsigned __int8 *)this + 73);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v67) = 0;
      v43 = *((_QWORD *)this + 7);
      if ( v43 && *(_QWORD *)(v43 + 16) )
        v44 = *(unsigned int *)(v43 + 16);
      else
        v44 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v67, v44);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v45 = *((_QWORD *)this + 7);
        LODWORD(v46) = v45 + 2120;
        if ( !v45 )
          v46 = &v66;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"SaveTcpipInfo... ",
          (_DWORD)v46,
          (v45 + 2686) & -(__int64)(v45 != 0),
          (__int64)&v67);
      }
    }
    LastError = SaveTcpipInfo(v13);
    if ( LastError )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_140;
      LOWORD(v71) = 0;
      LOWORD(v67) = 0;
      v48 = *((_QWORD *)this + 7);
      if ( v48 && *(_QWORD *)(v48 + 16) )
        v4 = *(_DWORD *)(v48 + 16);
      ConvertPortNoToString(&v67, v4);
      FormatRRASErrorString(&v71, L"SaveTcpipInfo failed %d", LastError);
    }
    else
    {
      v49 = *(_DWORD *)this;
      v50 = *((_DWORD *)a2 + 8);
      if ( !v50
        || (LastError = RasTcpSetRouteEx(v49 & v50, v49, v50, v47, lpWideCharStr, *(NET_LUID *)((char *)this + 48))) == 0 )
      {
        if ( *((_QWORD *)a2 + 6) )
        {
          if ( (byte_1800AA941 & 8) != 0 )
          {
            LOWORD(v67) = 0;
            v52 = *((_QWORD *)this + 7);
            if ( v52 && *(_QWORD *)(v52 + 16) )
              v4 = *(_DWORD *)(v52 + 16);
            ConvertPortNoToString(&v67, v4);
            if ( (byte_1800AA941 & 8) != 0 )
            {
              v53 = *((_QWORD *)this + 7);
              LODWORD(v54) = v53 + 2120;
              if ( !v53 )
                v54 = &v66;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceInfo,
                (unsigned int)L"Caching pbDhcpRoutes",
                (_DWORD)v54,
                (v53 + 2686) & -(__int64)(v53 != 0),
                (__int64)&v67);
            }
          }
          RasTcpSetDhcpRoutes(*((_QWORD *)a2 + 6), v49, 1);
          *((_QWORD *)this + 44) = *((_QWORD *)a2 + 6);
        }
        goto LABEL_140;
      }
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_140;
      LOWORD(v71) = 0;
      LOWORD(v67) = 0;
      v51 = *((_QWORD *)this + 7);
      if ( v51 && *(_QWORD *)(v51 + 16) )
        v4 = *(_DWORD *)(v51 + 16);
      ConvertPortNoToString(&v67, v4);
      FormatRRASErrorString(&v71, L"RasTcpSetRoute failed %d", LastError);
    }
    goto LABEL_21;
  }
  if ( (byte_1800AA941 & 4) == 0 )
    goto LABEL_140;
  LOWORD(v71) = 0;
  LOWORD(v67) = 0;
  v9 = *((_QWORD *)this + 7);
  if ( v9 && *(_QWORD *)(v9 + 16) )
    v4 = *(_DWORD *)(v9 + 16);
  ConvertPortNoToString(&v67, v4);
  FormatRRASErrorString(&v71, L"LoadTcpipInfo failed: %d", LastError);
LABEL_21:
  if ( (byte_1800AA941 & 4) != 0 )
  {
    v10 = *((_QWORD *)this + 7);
    LODWORD(v11) = v10 + 2120;
    if ( !v10 )
      v11 = &v66;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasVpnIkeParamTraceError,
      (unsigned int)&v71,
      (_DWORD)v11,
      (v10 + 2686) & -(__int64)(*((_QWORD *)this + 7) != 0),
      (__int64)&v67);
  }
LABEL_140:
  FreeTcpipInfo(&v59);
  LocalFree(*(HLOCAL *)a2);
  LocalFree(*((HLOCAL *)a2 + 5));
  LocalFree(*((HLOCAL *)a2 + 2));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_9b65cff8e2b438daa92b03f64bab9903_Traceguids, LastError);
  }
  v55 = LastError;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v60);
  return v55;
}

```

## disassembly

```asm
0x18004baa8  mov     [rsp-8+arg_10], rbx
0x18004baad  push    rbp
0x18004baae  push    rsi
0x18004baaf  push    rdi
0x18004bab0  push    r12
0x18004bab2  push    r13
0x18004bab4  push    r14
0x18004bab6  push    r15
0x18004bab8  lea     rbp, [rsp-7C0h]
0x18004bac0  sub     rsp, 8C0h
0x18004bac7  mov     rax, cs:__security_cookie
0x18004bace  xor     rax, rsp
0x18004bad1  mov     [rbp+7F0h+var_40], rax
0x18004bad8  mov     r12, rdx
0x18004badb  mov     rbx, rcx
0x18004bade  lea     rax, WPP_GLOBAL_Control
0x18004bae5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004baec  cmp     rcx, rax
0x18004baef  jz      short loc_18004BB12
0x18004baf1  test    byte ptr [rcx+1Ch], 1
0x18004baf5  jz      short loc_18004BB12
0x18004baf7  cmp     byte ptr [rcx+19h], 6
0x18004bafb  jb      short loc_18004BB12
0x18004bafd  mov     edx, 29h ; ')'
0x18004bb02  lea     r8, WPP_9b65cff8e2b438daa92b03f64bab9903_Traceguids
0x18004bb09  mov     rcx, [rcx+10h]
0x18004bb0d  call    WPP_SF_
0x18004bb12  xor     r13d, r13d
0x18004bb15  mov     [rsp+8F0h+var_8B8], r13
0x18004bb1a  mov     [rsp+8F0h+var_8C0], r13d
0x18004bb1f  mov     [rbp+7F0h+var_840], r13d
0x18004bb23  xor     edx, edx; Val
0x18004bb25  mov     r8d, 7FCh; Size
0x18004bb2b  lea     rcx, [rbp+7F0h+var_83C]; void *
0x18004bb2f  call    memset_0
0x18004bb34  mov     [rbp+7F0h+var_868], r13d
0x18004bb38  xorps   xmm0, xmm0
0x18004bb3b  xor     eax, eax
0x18004bb3d  movups  [rbp+7F0h+var_864], xmm0
0x18004bb41  movups  [rbp+7F0h+var_854], xmm0
0x18004bb45  mov     [rbp+7F0h+var_844], eax
0x18004bb48  movups  [rsp+8F0h+var_878], xmm0
0x18004bb4d  xorps   xmm1, xmm1
0x18004bb50  movdqu  [rsp+8F0h+var_8A8], xmm1
0x18004bb56  mov     [rsp+8F0h+var_8B0], r13
0x18004bb5b  movdqu  [rsp+8F0h+var_898], xmm0
0x18004bb61  mov     [rsp+8F0h+var_888], r13
0x18004bb66  or      edi, 0FFFFFFFFh
0x18004bb69  mov     [rsp+8F0h+var_880], edi
0x18004bb6d  mov     [rsp+8F0h+var_87C], r13d
0x18004bb72  mov     al, cs:byte_1800AA941
0x18004bb78  mov     sil, 8
0x18004bb7b  test    sil, al
0x18004bb7e  jz      loc_18004BC4C
0x18004bb84  mov     rax, [rbx+38h]
0x18004bb88  mov     [rsp+8F0h+lpWideCharStr], rax; void *
0x18004bb8d  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18004bb94  lea     r8, [rsp+8F0h+var_8C0]; unsigned int *
0x18004bb99  lea     rdx, aIpv4helperProc; "IPv4Helper::ProcessDHCPInform"
0x18004bba0  lea     rcx, [rsp+8F0h+var_8B0]; this
0x18004bba5  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18004bbaa  mov     al, cs:byte_1800AA941
0x18004bbb0  test    sil, al
0x18004bbb3  jz      loc_18004BC4C
0x18004bbb9  mov     word ptr [rbp+7F0h+var_840], r13w
0x18004bbbe  mov     word ptr [rbp+7F0h+var_868], r13w
0x18004bbc3  mov     rax, [rbx+38h]
0x18004bbc7  test    rax, rax
0x18004bbca  jz      short loc_18004BBD7
0x18004bbcc  cmp     [rax+10h], r13
0x18004bbd0  jz      short loc_18004BBD7
0x18004bbd2  mov     edx, [rax+10h]
0x18004bbd5  jmp     short loc_18004BBD9
0x18004bbd7  mov     edx, edi
0x18004bbd9  lea     rcx, [rbp+7F0h+var_868]
0x18004bbdd  call    ConvertPortNoToString
0x18004bbe2  mov     r8, [r12]
0x18004bbe6  lea     rdx, aDhcpinformRetu; "DHCPInform returned Device=%ws)"
0x18004bbed  lea     rcx, [rbp+7F0h+var_840]
0x18004bbf1  call    FormatRRASErrorString
0x18004bbf6  test    cs:byte_1800AA941, sil
0x18004bbfd  jz      short loc_18004BC4C
0x18004bbff  mov     rdx, [rbx+38h]
0x18004bc03  mov     rax, rdx
0x18004bc06  lea     rcx, [rdx+0A7Eh]
0x18004bc0d  neg     rax
0x18004bc10  sbb     r8, r8
0x18004bc13  and     r8, rcx
0x18004bc16  test    rdx, rdx
0x18004bc19  lea     r9, [rdx+848h]
0x18004bc20  jnz     short loc_18004BC27
0x18004bc22  lea     r9, [rsp+8F0h+var_878]
0x18004bc27  lea     rax, [rbp+7F0h+var_868]
0x18004bc2b  mov     qword ptr [rsp+8F0h+cchWideChar], rax
0x18004bc30  mov     [rsp+8F0h+lpWideCharStr], r8
0x18004bc35  lea     r8, [rbp+7F0h+var_840]
0x18004bc39  lea     rdx, RasVpnIkeParamTraceInfo
0x18004bc40  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004bc47  call    McTemplateU0zjzz_EventWriteTransfer
0x18004bc4c  xor     r8d, r8d
0x18004bc4f  mov     rdx, [r12]
0x18004bc53  lea     rcx, [rsp+8F0h+var_8B8]
0x18004bc58  call    LoadTcpipInfo
0x18004bc5d  mov     [rsp+8F0h+var_8C0], eax
0x18004bc61  test    eax, eax
0x18004bc63  jz      loc_18004BD11
0x18004bc69  test    cs:byte_1800AA941, 4
0x18004bc70  jz      loc_18004C3E5
0x18004bc76  mov     word ptr [rbp+7F0h+var_840], r13w
0x18004bc7b  mov     word ptr [rbp+7F0h+var_868], r13w
0x18004bc80  mov     rax, [rbx+38h]
0x18004bc84  test    rax, rax
0x18004bc87  jz      short loc_18004BC92
0x18004bc89  cmp     [rax+10h], r13
0x18004bc8d  jz      short loc_18004BC92
0x18004bc8f  mov     edi, [rax+10h]
0x18004bc92  mov     edx, edi
0x18004bc94  lea     rcx, [rbp+7F0h+var_868]
0x18004bc98  call    ConvertPortNoToString
0x18004bc9d  lea     rdx, aLoadtcpipinfoF_0; "LoadTcpipInfo failed: %d"
0x18004bca4  mov     r8d, [rsp+8F0h+var_8C0]
0x18004bca9  lea     rcx, [rbp+7F0h+var_840]
0x18004bcad  call    FormatRRASErrorString
0x18004bcb2  test    cs:byte_1800AA941, 4
0x18004bcb9  jz      loc_18004C3E5
0x18004bcbf  mov     rdx, [rbx+38h]
0x18004bcc3  mov     rax, rdx
0x18004bcc6  neg     rax
0x18004bcc9  lea     rcx, [rdx+0A7Eh]
0x18004bcd0  sbb     r8, r8
0x18004bcd3  and     r8, rcx
0x18004bcd6  lea     r9, [rdx+848h]
0x18004bcdd  test    rdx, rdx
0x18004bce0  jnz     short loc_18004BCE7
0x18004bce2  lea     r9, [rsp+8F0h+var_878]
0x18004bce7  lea     rax, [rbp+7F0h+var_868]
0x18004bceb  mov     qword ptr [rsp+8F0h+cchWideChar], rax
0x18004bcf0  mov     [rsp+8F0h+lpWideCharStr], r8
0x18004bcf5  lea     r8, [rbp+7F0h+var_840]
0x18004bcf9  lea     rdx, RasVpnIkeParamTraceError
0x18004bd00  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004bd07  call    McTemplateU0zjzz_EventWriteTransfer
0x18004bd0c  jmp     loc_18004C3E5
0x18004bd11  lea     r15, qword_18007E870
0x18004bd18  mov     r14, [rsp+8F0h+var_8B8]
0x18004bd1d  test    cs:byte_1800AA941, sil
0x18004bd24  jz      loc_18004BDC5
0x18004bd2a  mov     word ptr [rbp+7F0h+var_840], r13w
0x18004bd2f  mov     word ptr [rbp+7F0h+var_868], r13w
0x18004bd34  mov     rax, [rbx+38h]
0x18004bd38  test    rax, rax
0x18004bd3b  jz      short loc_18004BD48
0x18004bd3d  cmp     [rax+10h], r13
0x18004bd41  jz      short loc_18004BD48
0x18004bd43  mov     edx, [rax+10h]
0x18004bd46  jmp     short loc_18004BD4A
0x18004bd48  mov     edx, edi
0x18004bd4a  lea     rcx, [rbp+7F0h+var_868]
0x18004bd4e  call    ConvertPortNoToString
0x18004bd53  mov     r8, r15
0x18004bd56  cmp     [r14+68h], r13
0x18004bd5a  cmovnz  r8, [r14+68h]
0x18004bd5f  lea     rdx, aOldDnsWs; "Old Dns=%ws"
0x18004bd66  lea     rcx, [rbp+7F0h+var_840]
0x18004bd6a  call    FormatRRASErrorString
0x18004bd6f  test    cs:byte_1800AA941, sil
0x18004bd76  jz      short loc_18004BDC5
0x18004bd78  mov     rdx, [rbx+38h]
0x18004bd7c  mov     rax, rdx
0x18004bd7f  lea     rcx, [rdx+0A7Eh]
0x18004bd86  neg     rax
0x18004bd89  sbb     r8, r8
0x18004bd8c  and     r8, rcx
0x18004bd8f  test    rdx, rdx
0x18004bd92  lea     r9, [rdx+848h]
0x18004bd99  jnz     short loc_18004BDA0
0x18004bd9b  lea     r9, [rsp+8F0h+var_878]
0x18004bda0  lea     rax, [rbp+7F0h+var_868]
0x18004bda4  mov     qword ptr [rsp+8F0h+cchWideChar], rax
0x18004bda9  mov     [rsp+8F0h+lpWideCharStr], r8
0x18004bdae  lea     r8, [rbp+7F0h+var_840]
0x18004bdb2  lea     rdx, RasVpnIkeParamTraceInfo
0x18004bdb9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004bdc0  call    McTemplateU0zjzz_EventWriteTransfer
0x18004bdc5  mov     esi, [r12+8]
0x18004bdca  test    esi, esi
0x18004bdcc  jz      short loc_18004BE45
0x18004bdce  dec     esi
0x18004bdd0  mov     rax, [r12+10h]
0x18004bdd5  mov     r8d, [rax+rsi*4]
0x18004bdd9  lea     rcx, [r14+68h]
0x18004bddd  mov     rax, [rcx]
0x18004bde0  test    rax, rax
0x18004bde3  jz      short loc_18004BDF5
0x18004bde5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004bde9  inc     rdx
0x18004bdec  cmp     [rax+rdx*2], r13w
0x18004bdf1  jnz     short loc_18004BDE9
0x18004bdf3  jmp     short loc_18004BDF8
0x18004bdf5  mov     rdx, r13
0x18004bdf8  call    PrependDwIpAddress
0x18004bdfd  mov     [rsp+8F0h+var_8C0], eax
0x18004be01  test    eax, eax
0x18004be03  jz      short loc_18004BDCA
0x18004be05  test    cs:byte_1800AA941, 4
0x18004be0c  jz      loc_18004C3E5
0x18004be12  mov     word ptr [rbp+7F0h+var_840], r13w
0x18004be17  mov     word ptr [rbp+7F0h+var_868], r13w
0x18004be1c  mov     rax, [rbx+38h]
0x18004be20  test    rax, rax
0x18004be23  jz      short loc_18004BE2E
0x18004be25  cmp     [rax+10h], r13
0x18004be29  jz      short loc_18004BE2E
0x18004be2b  mov     edi, [rax+10h]
0x18004be2e  mov     edx, edi
0x18004be30  lea     rcx, [rbp+7F0h+var_868]
0x18004be34  call    ConvertPortNoToString
0x18004be39  lea     rdx, aDnsPrependdwip; "DNS PrependDwIpAddress failed: %d"
0x18004be40  jmp     loc_18004BCA4
0x18004be45  mov     al, cs:byte_1800AA941
0x18004be4b  test    al, 8
0x18004be4d  jz      loc_18004BEFB
0x18004be53  mov     word ptr [rbp+7F0h+var_840], r13w
0x18004be58  mov     word ptr [rbp+7F0h+var_868], r13w
0x18004be5d  mov     rax, [rbx+38h]
0x18004be61  test    rax, rax
0x18004be64  jz      short loc_18004BE71
0x18004be66  cmp     [rax+10h], r13
0x18004be6a  jz      short loc_18004BE71
0x18004be6c  mov     edx, [rax+10h]
0x18004be6f  jmp     short loc_18004BE73
0x18004be71  mov     edx, edi
0x18004be73  lea     rcx, [rbp+7F0h+var_868]
0x18004be77  call    ConvertPortNoToString
0x18004be7c  cmp     [r14+68h], r13
0x18004be80  cmovnz  r15, [r14+68h]
0x18004be85  mov     r8, r15
0x18004be88  lea     rdx, aProcesdhcpinfo; "ProcesDHCPInform: New Dns=%ws"
0x18004be8f  lea     rcx, [rbp+7F0h+var_840]
0x18004be93  call    FormatRRASErrorString
0x18004be98  mov     al, cs:byte_1800AA941
0x18004be9e  mov     r15b, 8
0x18004bea1  test    r15b, al
0x18004bea4  jz      short loc_18004BEFE
0x18004bea6  mov     rdx, [rbx+38h]
0x18004beaa  mov     rax, rdx
0x18004bead  lea     rcx, [rdx+0A7Eh]
0x18004beb4  neg     rax
0x18004beb7  sbb     r8, r8
0x18004beba  and     r8, rcx
0x18004bebd  test    rdx, rdx
0x18004bec0  lea     r9, [rdx+848h]
0x18004bec7  jnz     short loc_18004BECE
0x18004bec9  lea     r9, [rsp+8F0h+var_878]
0x18004bece  lea     rax, [rbp+7F0h+var_868]
0x18004bed2  mov     qword ptr [rsp+8F0h+cchWideChar], rax
0x18004bed7  mov     [rsp+8F0h+lpWideCharStr], r8
0x18004bedc  lea     r8, [rbp+7F0h+var_840]
0x18004bee0  lea     rdx, RasVpnIkeParamTraceInfo
0x18004bee7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004beee  call    McTemplateU0zjzz_EventWriteTransfer
0x18004bef3  mov     al, cs:byte_1800AA941
0x18004bef9  jmp     short loc_18004BEFE
0x18004befb  mov     r15b, 8
0x18004befe  cmp     [r12+18h], r13d
0x18004bf03  jz      loc_18004BFBF
0x18004bf09  mov     edx, [r12+1Ch]
0x18004bf0e  test    edx, edx
0x18004bf10  jz      short loc_18004BF63
0x18004bf12  lea     rcx, [r14+70h]
0x18004bf16  call    PrependDwIpAddressToMwsz
0x18004bf1b  mov     [rsp+8F0h+var_8C0], eax
0x18004bf1f  test    eax, eax
0x18004bf21  jz      short loc_18004BF63
0x18004bf23  test    cs:byte_1800AA941, 4
0x18004bf2a  jz      loc_18004C3E5
0x18004bf30  mov     word ptr [rbp+7F0h+var_840], r13w
0x18004bf35  mov     word ptr [rbp+7F0h+var_868], r13w
0x18004bf3a  mov     rax, [rbx+38h]
0x18004bf3e  test    rax, rax
0x18004bf41  jz      short loc_18004BF4C
0x18004bf43  cmp     [rax+10h], r13
0x18004bf47  jz      short loc_18004BF4C
0x18004bf49  mov     edi, [rax+10h]
0x18004bf4c  mov     edx, edi
0x18004bf4e  lea     rcx, [rbp+7F0h+var_868]
0x18004bf52  call    ConvertPortNoToString
0x18004bf57  lea     rdx, aWins2Prependdw; "WINS2 PrependDwIpAddressToMwsz failed: "...
0x18004bf5e  jmp     loc_18004BCA4
0x18004bf63  lea     rcx, [r14+70h]
0x18004bf67  mov     edx, [r12+18h]
0x18004bf6c  call    PrependDwIpAddressToMwsz
0x18004bf71  mov     [rsp+8F0h+var_8C0], eax
0x18004bf75  test    eax, eax
0x18004bf77  jz      short loc_18004BFB9
0x18004bf79  test    cs:byte_1800AA941, 4
0x18004bf80  jz      loc_18004C3E5
0x18004bf86  mov     word ptr [rbp+7F0h+var_840], r13w
0x18004bf8b  mov     word ptr [rbp+7F0h+var_868], r13w
0x18004bf90  mov     rax, [rbx+38h]
  ... truncated ...
```
