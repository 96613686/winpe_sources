# IPv6Helper::ActivateRoute(ushort *,ushort *)

- ea: `0x18004d640`
- end: `0x18004e5b5`
- name: `?ActivateRoute@IPv6Helper@@QEAAKPEAG0@Z`
- size: `3957`
- prototype: `__int64 __fastcall(IPv6Helper *this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18004fdf4`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x180009ee8`
- `0x180020ba4`
- `0x180039fa8`
- `0x18004cf08`
- `0x18004d640`
- `0x1800699e0`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x180077620`
- `0x18007a010`

## import_xrefs

- `msvcrt!wcschr` at `0x18004e166`
- `msvcrt!wcschr` at `0x18004e166`
- `rasman!RasAllocInterfaceLuidIndex` at `0x18004d9ce`
- `rasman!RasAllocInterfaceLuidIndex` at `0x18004d9ce`

## string_xrefs

- `0x18004de5c`: `NsiGetCompartmentIdForRoutingDomain failed:%d`
- `0x18004d84f`: `Failed to Acquire IP address for the demand dial interface. Error:%d. Will continue using link local address.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IPv6Helper::ActivateRoute(IPv6Helper *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  char *p_pszDest; // r15
  size_t v7; // r12
  __int64 v8; // rsi
  struct in6_addr v9; // xmm7
  unsigned int v10; // edi
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int128 *v14; // r9
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int128 *v18; // r9
  struct in6_addr v19; // xmm6
  unsigned int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int128 *v26; // r9
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int128 *v30; // r9
  __int64 v31; // rsi
  int v32; // r14d
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int128 *v36; // r9
  __int64 v37; // r8
  const wchar_t *v38; // r8
  __int128 *v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int128 *v43; // r9
  char *v44; // rcx
  size_t v45; // rdx
  __int64 v46; // rsi
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rdx
  __int128 *v50; // r9
  __int64 v51; // rcx
  __int64 v52; // rax
  int v53; // esi
  __int64 v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rdx
  __int128 *v57; // r9
  wchar_t *v58; // rax
  __int64 v59; // rax
  __int64 v60; // rdx
  __int128 *v61; // r9
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rdx
  __int128 *v65; // r9
  char *v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rdx
  unsigned int v70; // ebx
  int dwFlags; // [rsp+20h] [rbp-E0h]
  unsigned int CompartmentIdForRoutingDomain; // [rsp+40h] [rbp-C0h] BYREF
  STRSAFE_LPSTR ppszDestEnd; // [rsp+48h] [rbp-B8h] BYREF
  int v75; // [rsp+50h] [rbp-B0h]
  _DWORD v76[3]; // [rsp+54h] [rbp-ACh] BYREF
  struct in6_addr v77; // [rsp+60h] [rbp-A0h] BYREF
  struct in6_addr v78; // [rsp+70h] [rbp-90h] BYREF
  __int64 v79; // [rsp+80h] [rbp-80h] BYREF
  __int128 v80; // [rsp+88h] [rbp-78h]
  __int128 v81; // [rsp+98h] [rbp-68h]
  __int64 v82; // [rsp+A8h] [rbp-58h]
  int v83; // [rsp+B0h] [rbp-50h]
  int v84; // [rsp+B4h] [rbp-4Ch]
  size_t pcchRemaining; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v86; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v87[262]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v88[2]; // [rsp+1D6h] [rbp+D6h] BYREF
  wchar_t Str[128]; // [rsp+1D8h] [rbp+D8h] BYREF
  _DWORD v90[138]; // [rsp+2D8h] [rbp+1D8h] BYREF
  int v91; // [rsp+500h] [rbp+400h] BYREF
  __int128 v92; // [rsp+504h] [rbp+404h]
  __int128 v93; // [rsp+514h] [rbp+414h]
  int v94; // [rsp+524h] [rbp+424h]
  int v95; // [rsp+530h] [rbp+430h] BYREF
  _BYTE v96[2044]; // [rsp+534h] [rbp+434h] BYREF
  int v97; // [rsp+D30h] [rbp+C30h] BYREF
  unsigned int v98; // [rsp+D34h] [rbp+C34h]
  int v99; // [rsp+D38h] [rbp+C38h]
  int v100; // [rsp+D3Ch] [rbp+C3Ch]
  int v101; // [rsp+D40h] [rbp+C40h]
  int v102; // [rsp+D44h] [rbp+C44h]
  int v103; // [rsp+D64h] [rbp+C64h]
  _DWORD v104[5]; // [rsp+F80h] [rbp+E80h]
  _BYTE v105[28]; // [rsp+F94h] [rbp+E94h]
  wchar_t v106[274]; // [rsp+FB0h] [rbp+EB0h] BYREF
  __int128 v107; // [rsp+11D4h] [rbp+10D4h]
  char pszDest; // [rsp+11F0h] [rbp+10F0h] BYREF
  _BYTE v109[1023]; // [rsp+11F1h] [rbp+10F1h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_66f280efc6d63f258d12e6ab97837239_Traceguids);
  }
  CompartmentIdForRoutingDomain = 0;
  memset_0(v87, 0, 0x428u);
  pszDest = 0;
  memset_0(v109, 0, sizeof(v109));
  p_pszDest = &pszDest;
  ppszDestEnd = &pszDest;
  v7 = 1024;
  pcchRemaining = 1024;
  v8 = *((_QWORD *)this + 16);
  v75 = *(_DWORD *)(v8 + 1472);
  v76[0] = 0;
  v9 = *(struct in6_addr *)(v8 + 2120);
  v95 = 0;
  memset_0(v96, 0, sizeof(v96));
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v94 = 0;
  v86 = 0;
  v80 = 0;
  v79 = 0;
  v81 = 0;
  v82 = 0;
  v10 = -1;
  v83 = -1;
  v84 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v79,
      L"IPv6Helper::ActivateRoute",
      &CompartmentIdForRoutingDomain,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      (void *)v8);
  if ( v75 == 2 )
  {
    if ( *((_DWORD *)this + 101) )
    {
      if ( !IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)((char *)this + 52)) )
      {
        v77 = *(struct in6_addr *)this;
        CompartmentIdForRoutingDomain = IPv6Helper::AcquireIPAddressForClient(
                                          this,
                                          &v77,
                                          (struct in6_addr *)this,
                                          a2,
                                          a3);
        if ( CompartmentIdForRoutingDomain )
        {
          if ( (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v95) = 0;
            LOWORD(v91) = 0;
            v11 = *((_QWORD *)this + 16);
            if ( v11 && *(_QWORD *)(v11 + 16) )
              v12 = *(unsigned int *)(v11 + 16);
            else
              v12 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v91, v12);
            FormatRRASErrorString(
              &v95,
              L"Failed to Acquire IP address for the demand dial interface. Error:%d. Will continue using link local address.",
              CompartmentIdForRoutingDomain);
            if ( (byte_1800AA941 & 4) != 0 )
            {
              v13 = *((_QWORD *)this + 16);
              LODWORD(v14) = v13 + 2120;
              if ( !v13 )
                v14 = &v86;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceError,
                (unsigned int)&v95,
                (_DWORD)v14,
                (v13 + 2686) & -(__int64)(v13 != 0),
                (__int64)&v91);
            }
          }
          CompartmentIdForRoutingDomain = 0;
        }
      }
    }
  }
  CompartmentIdForRoutingDomain = (*((__int64 (__fastcall **)(_QWORD, __int64, __int64, _BYTE *))&xmmword_1800AA960 + 1))(
                                    *(_QWORD *)(*((_QWORD *)this + 16) + 16LL),
                                    34525,
                                    1,
                                    v87);
  if ( CompartmentIdForRoutingDomain )
  {
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_164;
    LOWORD(v95) = 0;
    LOWORD(v91) = 0;
    v15 = *((_QWORD *)this + 16);
    if ( v15 && *(_QWORD *)(v15 + 16) )
      v10 = *(_DWORD *)(v15 + 16);
    ConvertPortNoToString(&v91, v10);
    FormatRRASErrorString(&v95, L"RasAllocateRoute failed: %d", CompartmentIdForRoutingDomain);
    goto LABEL_27;
  }
  *((_DWORD *)this + 106) |= 4u;
  if ( v75 == 2 )
  {
    v19 = *(struct in6_addr *)this;
    v77 = *(struct in6_addr *)this;
    *((_DWORD *)this + 102) = 0;
  }
  else if ( *((_DWORD *)this + 101) )
  {
    v19 = *(struct in6_addr *)((char *)this + 52);
    v77 = v19;
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 52) + 56LL))((char *)this + 408);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v95) = 0;
      LOWORD(v91) = 0;
      v27 = *((_QWORD *)this + 16);
      if ( v27 && *(_QWORD *)(v27 + 16) )
        v28 = *(unsigned int *)(v27 + 16);
      else
        v28 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v91, v28);
      FormatRRASErrorString(
        &v95,
        L"GetNewSubInterfaceIndex returns %u as the SubInterfaceIndex",
        *((unsigned int *)this + 102));
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v29 = *((_QWORD *)this + 16);
        LODWORD(v30) = v29 + 2120;
        if ( !v29 )
          v30 = &v86;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v95,
          (_DWORD)v30,
          (v29 + 2686) & -(__int64)(v29 != 0),
          (__int64)&v91);
      }
    }
  }
  else
  {
    v19 = *(struct in6_addr *)this;
    v77 = *(struct in6_addr *)this;
    v20 = RasAllocInterfaceLuidIndex(*(_QWORD *)(*((_QWORD *)this + 16) + 16LL), v90);
    CompartmentIdForRoutingDomain = v20;
    v21 = v90[0];
    *((_DWORD *)this + 108) = v90[0];
    if ( v20 )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_164;
      LOWORD(v95) = 0;
      LOWORD(v91) = 0;
      v22 = *((_QWORD *)this + 16);
      if ( v22 && *(_QWORD *)(v22 + 16) )
        v10 = *(_DWORD *)(v22 + 16);
      ConvertPortNoToString(&v91, v10);
      FormatRRASErrorString(&v95, L"RasAllocInterfaceLuidIndex failed: %d", CompartmentIdForRoutingDomain);
LABEL_27:
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v16 = *((_QWORD *)this + 16);
        v17 = (v16 + 2686) & -(__int64)(v16 != 0);
        LODWORD(v18) = v16 + 2120;
        if ( !v16 )
          v18 = &v86;
LABEL_163:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v95,
          (_DWORD)v18,
          v17,
          (__int64)&v91);
        goto LABEL_164;
      }
      goto LABEL_164;
    }
    *((_WORD *)this + 63) = 23;
    *((_QWORD *)this + 15) = (v21 << 24) ^ (*((_QWORD *)this + 15) ^ (v21 << 24)) & 0xFFFF000000000000uLL;
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v95) = 0;
      LOWORD(v91) = 0;
      v23 = *((_QWORD *)this + 16);
      if ( v23 && *(_QWORD *)(v23 + 16) )
        v24 = *(unsigned int *)(v23 + 16);
      else
        v24 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v91, v24);
      FormatRRASErrorString(&v95, L"RasAllocInterfaceLuidIndex returns LuidIndex:%I64X", *((_QWORD *)this + 15));
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v25 = *((_QWORD *)this + 16);
        LODWORD(v26) = v25 + 2120;
        if ( !v25 )
          v26 = &v86;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v95,
          (_DWORD)v26,
          (v25 + 2686) & -(__int64)(v25 != 0),
          (__int64)&v91);
      }
    }
    *((_DWORD *)this + 106) |= 2u;
  }
  v31 = 0;
  while ( 1 )
  {
    StringCchPrintfExA(p_pszDest, v7, &ppszDestEnd, &pcchRemaining, 0x100u, "%02X ", v77.u.Byte[v31++]);
    if ( v31 == 16 )
      break;
    p_pszDest = ppszDestEnd;
    v7 = pcchRemaining;
  }
  v32 = v75;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v95) = 0;
    LOWORD(v91) = 0;
    v33 = *((_QWORD *)this + 16);
    if ( v33 && *(_QWORD *)(v33 + 16) )
      v34 = *(unsigned int *)(v33 + 16);
    else
      v34 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v91, v34);
    FormatRRASErrorString(&v95, L"Addr =%S", &pszDest);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v35 = *((_QWORD *)this + 16);
      LODWORD(v36) = v35 + 2120;
      if ( !v35 )
        v36 = &v86;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceInfo,
        (unsigned int)&v95,
        (_DWORD)v36,
        (v35 + 2686) & -(__int64)(v35 != 0),
        (__int64)&v91);
    }
  }
  v90[133] = 0;
  v97 = 1200;
  if ( v32 == 2 )
  {
    v98 = 2;
    v101 = *(_DWORD *)(*((_QWORD *)this + 16) + 1488LL);
  }
  else
  {
    v98 = *((_DWORD *)this + 101) == 0;
    v101 = -1;
  }
  v102 = *((_DWORD *)this + 102);
  v99 = 1;
  v100 = 1;
  v37 = *((_QWORD *)this + 16);
  *(_QWORD *)&v104[3] = *(_QWORD *)(v37 + 8);
  *(_QWORD *)v104 = _mm_srli_si128((__m128i)v19, 8).m128i_u64[0];
  if ( *a2 )
  {
    v38 = a2;
LABEL_77:
    StringCchCopyW(v106, 0x111u, v38);
    goto LABEL_79;
  }
  v38 = (const wchar_t *)(v37 + 2686);
  if ( *v38 )
    goto LABEL_77;
  v106[0] = 0;
LABEL_79:
  v39 = (__int128 *)(*((_QWORD *)this + 16) + 2120LL);
  v107 = *v39;
  CompartmentIdForRoutingDomain = NsiGetCompartmentIdForRoutingDomain(v39, v76);
  if ( CompartmentIdForRoutingDomain )
  {
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v95) = 0;
      LOWORD(v91) = 0;
      v40 = *((_QWORD *)this + 16);
      if ( v40 && *(_QWORD *)(v40 + 16) )
        v41 = *(unsigned int *)(v40 + 16);
      else
        v41 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v91, v41);
      FormatRRASErrorString(&v95, L"NsiGetCompartmentIdForRoutingDomain failed:%d", CompartmentIdForRoutingDomain);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v42 = *((_QWORD *)this + 16);
        LODWORD(v43) = v42 + 2120;
        if ( !v42 )
          v43 = &v86;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v95,
          (_DWORD)v43,
          (v42 + 2686) & -(__int64)(v42 != 0),
          (__int64)&v91);
      }
    }
    CompartmentIdForRoutingDomain = 0;
  }
  v103 = v76[0];
  v44 = &pszDest;
  ppszDestEnd = &pszDest;
  v45 = 1024;
  pcchRemaining = 1024;
  v46 = 0;
  while ( 1 )
  {
    StringCchPrintfExA(v44, v45, &ppszDestEnd, &pcchRemaining, 0x100u, "%02X ", *((unsigned __int8 *)v104 + v46++));
    if ( v46 == 8 )
      break;
    v44 = ppszDestEnd;
    v45 = pcchRemaining;
  }
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v95) = 0;
    LOWORD(v91) = 0;
    v47 = *((_QWORD *)this + 16);
    if ( v47 && *(_QWORD *)(v47 + 16) )
      v48 = *(unsigned int *)(v47 + 16);
    else
      v48 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v91, v48);
    FormatRRASErrorString(&v95, L"LocalId %S", &pszDest);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v49 = *((_QWORD *)this + 16);
      LODWORD(v50) = v49 + 2120;
      if ( !v49 )
        v50 = &v86;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceInfo,
        (unsigned int)&v95,
        (_DWORD)v50,
        (v49 + 2686) & -(__int64)(v49 != 0),
        (__int64)&v91);
    }
  }
  v51 = *((_QWORD *)this + 16);
  *(_OWORD *)v105 = *(_OWORD *)(v51 + 2136);
  *(_OWORD *)&v105[12] = *(_OWORD *)(v51 + 2148);
  CompartmentIdForRoutingDomain = (*((__int64 (__fastcall **)(_QWORD, __int64, _BYTE *, int *))&xmmword_1800AA9B0 + 1))(
                                    *(_QWORD *)(v51 + 16),
                                    34525,
                                    v87,
                                    &v97);
  if ( CompartmentIdForRoutingDomain )
  {
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_164;
    LOWORD(v95) = 0;
    LOWORD(v91) = 0;
    v52 = *((_QWORD *)this + 16);
    if ( v52 && *(_QWORD *)(v52 + 16) )
      v10 = *(_DWORD *)(v52 + 16);
    ConvertPortNoToString(&v91, v10);
    FormatRRASErrorString(&v95, L"RasActivateRoute failed: %d", CompartmentIdForRoutingDomain);
    goto LABEL_160;
  }
  v53 = 0;
  if ( v98 == 2 )
    v53 = v90[0];
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v95) = 0;
    LOWORD(v91) = 0;
    v54 = *((_QWORD *)this + 16);
    if ( v54 && *(_QWORD *)(v54 + 16) )
      v55 = *(unsigned int *)(v54 + 16);
    else
      v55 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v91, v55);
    FormatRRASErrorString(&v95, L"AdapterName: %ws", v88);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v56 = *((_QWORD *)this + 16);
      LODWORD(v57) = v56 + 2120;
      if ( !v56 )
        v57 = &v86;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceInfo,
        (unsigned int)&v95,
        (_DWORD)v57,
        (v56 + 2686) & -(__int64)(v56 != 0),
        (__int64)&v91);
    }
  }
  v58 = wcschr(Str, 0x5Cu);
  if ( !v58 )
  {
    CompartmentIdForRoutingDomain = 87;
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v91) = 0;
      v59 = *((_QWORD *)this + 16);
      if ( v59 && *(_QWORD *)(v59 + 16) )
        v10 = *(_DWORD *)(v59 + 16);
      ConvertPortNoToString(&v91, v10);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v60 = *((_QWORD *)this + 16);
        LODWORD(v61) = v60 + 2120;
        if ( !v60 )
          v61 = &v86;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Invalid AdapterName",
          (_DWORD)v61,
          (v60 + 2686) & -(__int64)(v60 != 0),
          (__int64)&v91);
      }
    }
    goto LABEL_164;
  }
  StringCchCopyW((STRSAFE_LPWSTR)this + 73, 0x80u, v58 + 1);
  if ( v32 != 2 )
  {
    if ( !*((_DWORD *)this + 101) )
      goto LABEL_164;
    goto LABEL_132;
  }
  if ( !IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)((char *)this + 52)) )
  {
LABEL_132:
    ppszDestEnd = 0;
    pcchRemaining = 0;
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v91) = 0;
      v62 = *((_QWORD *)this + 16);
      if ( v62 && *(_QWORD *)(v62 + 16) )
        v63 = *(unsigned int *)(v62 + 16);
      else
        v63 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v91, v63);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v64 = *((_QWORD *)this + 16);
        LODWORD(v65) = v64 + 2120;
        if ( !v64 )
          v65 = &v86;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"Activate IPv6 Address for client...",
          (_DWORD)v65,
          (v64 + 2686) & -(__int64)(v64 != 0),
          (__int64)&v91);
      }
    }
    if ( v32 == 2 || !*((_DWORD *)this + 101) )
    {
      v66 = (char *)((v53 & 0xFFFFFF | 0x17000000LL) << 24);
      *((_QWORD *)this + 15) = v66;
    }
    else
    {
      v66 = (char *)*((unsigned int *)this + 102);
    }
    ppszDestEnd = v66;
    pcchRemaining = *(_QWORD *)((char *)this + 60);
    v77 = v9;
    CompartmentIdForRoutingDomain = (*(__int64 (__fastcall **)(struct in6_addr *, _QWORD, size_t *, STRSAFE_LPSTR *, _DWORD))(*((_QWORD *)this + 52) + 64LL))(
                                      &v77,
                                      *(_QWORD *)(*((_QWORD *)this + 16) + 16LL),
                                      &pcchRemaining,
                                      &ppszDestEnd,
                                      *((_DWORD *)this + 107));
    if ( !CompartmentIdForRoutingDomain )
    {
      v77 = *(struct in6_addr *)((char *)this + 52);
      v78 = v9;
      LOBYTE(dwFlags) = v32 == 2;
      CompartmentIdForRoutingDomain = (*(__int64 (__fastcall **)(struct in6_addr *, struct in6_addr *, _QWORD, STRSAFE_LPSTR *, int))(*((_QWORD *)this + 52) + 80LL))(
                                        &v78,
                                        &v77,
                                        v98,
                                        &ppszDestEnd,
                                        dwFlags);
      if ( !CompartmentIdForRoutingDomain )
      {
        if ( v32 == 2 && *((_DWORD *)this + 101) )
        {
          v78 = *(struct in6_addr *)this;
          v77 = *(struct in6_addr *)((char *)this + 52);
          (*(void (__fastcall **)(struct in6_addr *, struct in6_addr *, STRSAFE_LPSTR *, _QWORD))(*((_QWORD *)this + 52)
                                                                                                + 160LL))(
            &v77,
            &v78,
            &ppszDestEnd,
            0);
        }
        goto LABEL_164;
      }
    }
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_164;
    v67 = *((_QWORD *)this + 16);
    LOWORD(v91) = 0;
    LOWORD(v95) = 0;
    if ( v67 && *(_QWORD *)(v67 + 16) )
      v10 = *(_DWORD *)(v67 + 16);
    ConvertPortNoToString(&v91, v10);
    FormatRRASErrorString(&v95, L" Activate Ipv6Address for client done %d", CompartmentIdForRoutingDomain);
    goto LABEL_160;
  }
  pcchRemaining = (v53 & 0xFFFFFF | 0x17000000LL) << 24;
  CompartmentIdForRoutingDomain = (*(__int64 (__fastcall **)(size_t *))(*((_QWORD *)this + 52) + 176LL))(&pcchRemaining);
  if ( (byte_1800AA941 & 4) == 0 )
    goto LABEL_164;
  LOWORD(v95) = 0;
  LOWORD(v91) = 0;
  v68 = *((_QWORD *)this + 16);
  if ( v68 && *(_QWORD *)(v68 + 16) )
    v10 = *(_DWORD *)(v68 + 16);
  ConvertPortNoToString(&v91, v10);
  FormatRRASErrorString(&v95, L"SetIpv6InterfacePropertiesUsingLuidForDD done %d", CompartmentIdForRoutingDomain);
LABEL_160:
  if ( (byte_1800AA941 & 4) != 0 )
  {
    v69 = *((_QWORD *)this + 16);
    v17 = (v69 + 2686) & -(__int64)(v69 != 0);
    LODWORD(v18) = v69 + 2120;
    if ( !v69 )
      v18 = &v86;
    goto LABEL_163;
  }
LABEL_164:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_66f280efc6d63f258d12e6ab97837239_Traceguids,
      CompartmentIdForRoutingDomain);
  }
  v70 = CompartmentIdForRoutingDomain;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v79);
  return v70;
}

```

## disassembly

```asm
0x18004d640  mov     [rsp-8+arg_18], rbx
0x18004d645  push    rbp
0x18004d646  push    rsi
0x18004d647  push    rdi
0x18004d648  push    r12
0x18004d64a  push    r13
0x18004d64c  push    r14
0x18004d64e  push    r15
0x18004d650  lea     rbp, [rsp-1520h]
0x18004d658  mov     eax, 1620h
0x18004d65d  call    _alloca_probe
0x18004d662  sub     rsp, rax
0x18004d665  movaps  [rsp+1650h+var_40], xmm6
0x18004d66d  movaps  [rsp+1650h+var_50], xmm7
0x18004d675  mov     rax, cs:__security_cookie
0x18004d67c  xor     rax, rsp
0x18004d67f  mov     [rbp+1550h+var_60], rax
0x18004d686  mov     r14, r8
0x18004d689  mov     r13, rdx
0x18004d68c  mov     rbx, rcx
0x18004d68f  lea     rax, WPP_GLOBAL_Control
0x18004d696  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d69d  cmp     rcx, rax
0x18004d6a0  jz      short loc_18004D6C3
0x18004d6a2  test    byte ptr [rcx+1Ch], 1
0x18004d6a6  jz      short loc_18004D6C3
0x18004d6a8  cmp     byte ptr [rcx+19h], 6
0x18004d6ac  jb      short loc_18004D6C3
0x18004d6ae  mov     edx, 11h
0x18004d6b3  lea     r8, WPP_66f280efc6d63f258d12e6ab97837239_Traceguids
0x18004d6ba  mov     rcx, [rcx+10h]
0x18004d6be  call    WPP_SF_
0x18004d6c3  xor     edi, edi
0x18004d6c5  mov     [rsp+1650h+var_1610], edi
0x18004d6c9  xor     edx, edx; Val
0x18004d6cb  mov     r8d, 428h; Size
0x18004d6d1  lea     rcx, [rbp+1550h+var_1580]; void *
0x18004d6d5  call    memset_0
0x18004d6da  mov     [rbp+1550h+pszDest], dil
0x18004d6e1  xor     edx, edx; Val
0x18004d6e3  mov     r8d, 3FFh; Size
0x18004d6e9  lea     rcx, [rbp+1550h+var_45F]; void *
0x18004d6f0  call    memset_0
0x18004d6f5  lea     r15, [rbp+1550h+pszDest]
0x18004d6fc  mov     [rsp+1650h+ppszDestEnd], r15
0x18004d701  mov     r12d, 400h
0x18004d707  mov     [rbp+1550h+pcchRemaining], r12
0x18004d70b  mov     rsi, [rbx+80h]
0x18004d712  mov     eax, [rsi+5C0h]
0x18004d718  mov     [rsp+1650h+var_1600], eax
0x18004d71c  mov     [rsp+1650h+var_15FC], edi
0x18004d720  movups  xmm7, xmmword ptr [rsi+848h]
0x18004d727  mov     [rbp+1550h+var_1120], edi
0x18004d72d  xor     edx, edx; Val
0x18004d72f  mov     r8d, 7FCh; Size
0x18004d735  lea     rcx, [rbp+1550h+var_111C]; void *
0x18004d73c  call    memset_0
0x18004d741  mov     [rbp+1550h+var_1150], edi
0x18004d747  xorps   xmm0, xmm0
0x18004d74a  xor     eax, eax
0x18004d74c  movups  [rbp+1550h+var_114C], xmm0
0x18004d753  movups  [rbp+1550h+var_113C], xmm0
0x18004d75a  mov     [rbp+1550h+var_112C], eax
0x18004d760  movups  [rbp+1550h+var_1590], xmm0
0x18004d764  xorps   xmm1, xmm1
0x18004d767  movdqu  [rbp+1550h+var_15C8], xmm1
0x18004d76c  mov     [rbp+1550h+var_15D0], rdi
0x18004d770  movdqu  [rbp+1550h+var_15B8], xmm0
0x18004d775  mov     [rbp+1550h+var_15A8], rdi
0x18004d779  or      edi, 0FFFFFFFFh
0x18004d77c  mov     [rbp+1550h+var_15A0], edi
0x18004d77f  mov     [rbp+1550h+var_159C], eax
0x18004d782  test    cs:byte_1800AA941, 8
0x18004d789  jz      short loc_18004D7AC
0x18004d78b  mov     qword ptr [rsp+1650h+dwFlags], rsi; void *
0x18004d790  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18004d797  lea     r8, [rsp+1650h+var_1610]; unsigned int *
0x18004d79c  lea     rdx, aIpv6helperActi; "IPv6Helper::ActivateRoute"
0x18004d7a3  lea     rcx, [rbp+1550h+var_15D0]; this
0x18004d7a7  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18004d7ac  mov     esi, 4
0x18004d7b1  cmp     [rsp+1650h+var_1600], 2
0x18004d7b6  jnz     loc_18004D8C8
0x18004d7bc  cmp     dword ptr [rbx+194h], 0
0x18004d7c3  jz      loc_18004D8C8
0x18004d7c9  lea     rcx, [rbx+34h]; a
0x18004d7cd  call    IN6_IS_ADDR_UNSPECIFIED
0x18004d7d2  test    al, al
0x18004d7d4  jnz     loc_18004D8C8
0x18004d7da  movups  xmm0, xmmword ptr [rbx]
0x18004d7dd  movdqu  xmmword ptr [rsp+1650h+var_15F0.u], xmm0
0x18004d7e3  mov     qword ptr [rsp+1650h+dwFlags], r14; unsigned __int16 *
0x18004d7e8  mov     r9, r13; unsigned __int16 *
0x18004d7eb  mov     r8, rbx; struct in6_addr *
0x18004d7ee  lea     rdx, [rsp+1650h+var_15F0]; struct in6_addr *
0x18004d7f3  mov     rcx, rbx; this
0x18004d7f6  call    ?AcquireIPAddressForClient@IPv6Helper@@QEAAKUin6_addr@@PEAU2@PEAG2@Z; IPv6Helper::AcquireIPAddressForClient(in6_addr,in6_addr *,ushort *,ushort *)
0x18004d7fb  mov     [rsp+1650h+var_1610], eax
0x18004d7ff  test    eax, eax
0x18004d801  jz      loc_18004D8C8
0x18004d807  test    cs:byte_1800AA941, sil
0x18004d80e  jz      loc_18004D8C0
0x18004d814  xor     eax, eax
0x18004d816  mov     word ptr [rbp+1550h+var_1120], ax
0x18004d81d  mov     word ptr [rbp+1550h+var_1150], ax
0x18004d824  mov     rax, [rbx+80h]
0x18004d82b  test    rax, rax
0x18004d82e  jz      short loc_18004D83C
0x18004d830  cmp     qword ptr [rax+10h], 0
0x18004d835  jz      short loc_18004D83C
0x18004d837  mov     edx, [rax+10h]
0x18004d83a  jmp     short loc_18004D83E
0x18004d83c  mov     edx, edi
0x18004d83e  lea     rcx, [rbp+1550h+var_1150]
0x18004d845  call    ConvertPortNoToString
0x18004d84a  mov     r8d, [rsp+1650h+var_1610]
0x18004d84f  lea     rdx, aFailedToAcquir; "Failed to Acquire IP address for the de"...
0x18004d856  lea     rcx, [rbp+1550h+var_1120]
0x18004d85d  call    FormatRRASErrorString
0x18004d862  test    cs:byte_1800AA941, sil
0x18004d869  jz      short loc_18004D8C0
0x18004d86b  mov     rdx, [rbx+80h]
0x18004d872  mov     rax, rdx
0x18004d875  lea     rcx, [rdx+0A7Eh]
0x18004d87c  neg     rax
0x18004d87f  sbb     r8, r8
0x18004d882  and     r8, rcx
0x18004d885  test    rdx, rdx
0x18004d888  lea     r9, [rdx+848h]
0x18004d88f  jnz     short loc_18004D895
0x18004d891  lea     r9, [rbp+1550h+var_1590]
0x18004d895  lea     rax, [rbp+1550h+var_1150]
0x18004d89c  mov     [rsp+1650h+pszFormat], rax
0x18004d8a1  mov     qword ptr [rsp+1650h+dwFlags], r8
0x18004d8a6  lea     r8, [rbp+1550h+var_1120]
0x18004d8ad  lea     rdx, RasVpnIkeParamTraceError
0x18004d8b4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004d8bb  call    McTemplateU0zjzz_EventWriteTransfer
0x18004d8c0  mov     [rsp+1650h+var_1610], 0
0x18004d8c8  mov     rcx, [rbx+80h]
0x18004d8cf  lea     r9, [rbp+1550h+var_1580]
0x18004d8d3  mov     edx, 86DDh
0x18004d8d8  mov     r8d, 1
0x18004d8de  mov     rcx, [rcx+10h]
0x18004d8e2  mov     rax, qword ptr cs:xmmword_1800AA960+8
0x18004d8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8ee  mov     [rsp+1650h+var_1610], eax
0x18004d8f2  test    eax, eax
0x18004d8f4  jz      loc_18004D996
0x18004d8fa  test    cs:byte_1800AA941, sil
0x18004d901  jz      loc_18004E539
0x18004d907  xor     eax, eax
0x18004d909  mov     word ptr [rbp+1550h+var_1120], ax
0x18004d910  mov     word ptr [rbp+1550h+var_1150], ax
0x18004d917  mov     rax, [rbx+80h]
0x18004d91e  test    rax, rax
0x18004d921  jz      short loc_18004D92D
0x18004d923  cmp     qword ptr [rax+10h], 0
0x18004d928  jz      short loc_18004D92D
0x18004d92a  mov     edi, [rax+10h]
0x18004d92d  mov     edx, edi
0x18004d92f  lea     rcx, [rbp+1550h+var_1150]
0x18004d936  call    ConvertPortNoToString
0x18004d93b  lea     rdx, aRasallocaterou; "RasAllocateRoute failed: %d"
0x18004d942  mov     r8d, [rsp+1650h+var_1610]
0x18004d947  lea     rcx, [rbp+1550h+var_1120]
0x18004d94e  call    FormatRRASErrorString
0x18004d953  test    cs:byte_1800AA941, sil
0x18004d95a  jz      loc_18004E539
0x18004d960  mov     rdx, [rbx+80h]
0x18004d967  mov     rax, rdx
0x18004d96a  lea     rcx, [rdx+0A7Eh]
0x18004d971  neg     rax
0x18004d974  sbb     r8, r8
0x18004d977  and     r8, rcx
0x18004d97a  test    rdx, rdx
0x18004d97d  lea     r9, [rdx+848h]
0x18004d984  jnz     short loc_18004D98A
0x18004d986  lea     r9, [rbp+1550h+var_1590]
0x18004d98a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004d991  jmp     loc_18004E515
0x18004d996  or      [rbx+1A8h], esi
0x18004d99c  cmp     [rsp+1650h+var_1600], 2
0x18004d9a1  jz      loc_18004DC01
0x18004d9a7  cmp     dword ptr [rbx+194h], 0
0x18004d9ae  jnz     loc_18004DB25
0x18004d9b4  movups  xmm6, xmmword ptr [rbx]
0x18004d9b7  movups  xmmword ptr [rsp+1650h+var_15F0.u], xmm6
0x18004d9bc  mov     rcx, [rbx+80h]
0x18004d9c3  lea     rdx, [rbp+1550h+var_1378]
0x18004d9ca  mov     rcx, [rcx+10h]
0x18004d9ce  call    cs:__imp_RasAllocInterfaceLuidIndex
0x18004d9d4  mov     [rsp+1650h+var_1610], eax
0x18004d9d8  mov     ecx, [rbp+1550h+var_1378]
0x18004d9de  mov     [rbx+1B0h], ecx
0x18004d9e4  test    eax, eax
0x18004d9e6  jz      short loc_18004DA35
0x18004d9e8  test    cs:byte_1800AA941, sil
0x18004d9ef  jz      loc_18004E539
0x18004d9f5  xor     eax, eax
0x18004d9f7  mov     word ptr [rbp+1550h+var_1120], ax
0x18004d9fe  mov     word ptr [rbp+1550h+var_1150], ax
0x18004da05  mov     rax, [rbx+80h]
0x18004da0c  test    rax, rax
0x18004da0f  jz      short loc_18004DA1B
0x18004da11  cmp     qword ptr [rax+10h], 0
0x18004da16  jz      short loc_18004DA1B
0x18004da18  mov     edi, [rax+10h]
0x18004da1b  mov     edx, edi
0x18004da1d  lea     rcx, [rbp+1550h+var_1150]
0x18004da24  call    ConvertPortNoToString
0x18004da29  lea     rdx, aRasallocinterf; "RasAllocInterfaceLuidIndex failed: %d"
0x18004da30  jmp     loc_18004D942
0x18004da35  mov     word ptr [rbx+7Eh], 17h
0x18004da3b  shl     rcx, 18h
0x18004da3f  mov     rax, rcx
0x18004da42  xor     rax, [rbx+78h]
0x18004da46  mov     rdx, 0FFFF000000000000h
0x18004da50  and     rax, rdx
0x18004da53  and     rcx, 0FFFFFFFFFF000000h
0x18004da5a  xor     rax, rcx
0x18004da5d  mov     [rbx+78h], rax
0x18004da61  test    cs:byte_1800AA941, 8
0x18004da68  jz      loc_18004DB19
0x18004da6e  xor     eax, eax
0x18004da70  mov     word ptr [rbp+1550h+var_1120], ax
0x18004da77  mov     word ptr [rbp+1550h+var_1150], ax
0x18004da7e  mov     rax, [rbx+80h]
0x18004da85  test    rax, rax
0x18004da88  jz      short loc_18004DA96
0x18004da8a  cmp     qword ptr [rax+10h], 0
0x18004da8f  jz      short loc_18004DA96
0x18004da91  mov     edx, [rax+10h]
0x18004da94  jmp     short loc_18004DA98
0x18004da96  mov     edx, edi
0x18004da98  lea     rcx, [rbp+1550h+var_1150]
0x18004da9f  call    ConvertPortNoToString
0x18004daa4  mov     r8, [rbx+78h]
0x18004daa8  lea     rdx, aRasallocinterf_0; "RasAllocInterfaceLuidIndex returns Luid"...
0x18004daaf  lea     rcx, [rbp+1550h+var_1120]
0x18004dab6  call    FormatRRASErrorString
0x18004dabb  test    cs:byte_1800AA941, 8
0x18004dac2  jz      short loc_18004DB19
0x18004dac4  mov     rdx, [rbx+80h]
0x18004dacb  mov     rax, rdx
0x18004dace  lea     rcx, [rdx+0A7Eh]
0x18004dad5  neg     rax
0x18004dad8  sbb     r8, r8
0x18004dadb  and     r8, rcx
0x18004dade  test    rdx, rdx
0x18004dae1  lea     r9, [rdx+848h]
0x18004dae8  jnz     short loc_18004DAEE
0x18004daea  lea     r9, [rbp+1550h+var_1590]
0x18004daee  lea     rax, [rbp+1550h+var_1150]
0x18004daf5  mov     [rsp+1650h+pszFormat], rax
0x18004dafa  mov     qword ptr [rsp+1650h+dwFlags], r8
0x18004daff  lea     r8, [rbp+1550h+var_1120]
0x18004db06  lea     rdx, RasVpnIkeParamTraceInfo
0x18004db0d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004db14  call    McTemplateU0zjzz_EventWriteTransfer
0x18004db19  or      dword ptr [rbx+1A8h], 2
0x18004db20  jmp     loc_18004DC13
0x18004db25  movups  xmm6, xmmword ptr [rbx+34h]
0x18004db29  movups  xmmword ptr [rsp+1650h+var_15F0.u], xmm6
0x18004db2e  lea     rsi, [rbx+198h]
0x18004db35  mov     rax, [rbx+1A0h]
0x18004db3c  mov     rcx, rsi
0x18004db3f  mov     rax, [rax+38h]
0x18004db43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004db48  test    cs:byte_1800AA941, 8
0x18004db4f  jz      loc_18004DC13
0x18004db55  xor     eax, eax
0x18004db57  mov     word ptr [rbp+1550h+var_1120], ax
0x18004db5e  mov     word ptr [rbp+1550h+var_1150], ax
0x18004db65  mov     rax, [rbx+80h]
0x18004db6c  test    rax, rax
0x18004db6f  jz      short loc_18004DB7D
0x18004db71  cmp     qword ptr [rax+10h], 0
0x18004db76  jz      short loc_18004DB7D
0x18004db78  mov     edx, [rax+10h]
0x18004db7b  jmp     short loc_18004DB7F
0x18004db7d  mov     edx, edi
0x18004db7f  lea     rcx, [rbp+1550h+var_1150]
0x18004db86  call    ConvertPortNoToString
0x18004db8b  mov     r8d, [rsi]
0x18004db8e  lea     rdx, aGetnewsubinter; "GetNewSubInterfaceIndex returns %u as t"...
0x18004db95  lea     rcx, [rbp+1550h+var_1120]
0x18004db9c  call    FormatRRASErrorString
0x18004dba1  test    cs:byte_1800AA941, 8
0x18004dba8  jz      short loc_18004DC13
0x18004dbaa  mov     rdx, [rbx+80h]
0x18004dbb1  mov     rax, rdx
0x18004dbb4  lea     rcx, [rdx+0A7Eh]
0x18004dbbb  neg     rax
0x18004dbbe  sbb     r8, r8
0x18004dbc1  and     r8, rcx
0x18004dbc4  test    rdx, rdx
0x18004dbc7  lea     r9, [rdx+848h]
0x18004dbce  jnz     short loc_18004DBD4
0x18004dbd0  lea     r9, [rbp+1550h+var_1590]
  ... truncated ...
```
