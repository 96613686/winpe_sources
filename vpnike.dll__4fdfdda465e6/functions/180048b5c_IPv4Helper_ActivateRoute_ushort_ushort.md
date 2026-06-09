# IPv4Helper::ActivateRoute(ushort *,ushort *)

- ea: `0x180048b5c`
- end: `0x180049714`
- name: `?ActivateRoute@IPv4Helper@@QEAAKPEAG0@Z`
- size: `3000`
- prototype: `__int64 __fastcall(IPv4Helper *this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18004b840`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x180020ba4`
- `0x180048684`
- `0x180048b5c`
- `0x18004b294`
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

- `msvcrt!wcschr` at `0x180049426`
- `msvcrt!wcschr` at `0x180049426`
- `rasman!RasAllocInterfaceLuidIndex` at `0x180048ea9`
- `rasman!RasAllocInterfaceLuidIndex` at `0x180048ea9`

## string_xrefs

- `0x18004918c`: `NsiGetCompartmentIdForRoutingDomain failed:%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IPv4Helper::ActivateRoute(IPv4Helper *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 v6; // rsi
  int v7; // r12d
  unsigned int v8; // edi
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int128 *v12; // r9
  __int64 v13; // rax
  __int64 v14; // rdx
  __int128 *v15; // r9
  unsigned int v16; // esi
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int128 *v21; // r9
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // r8
  const wchar_t *v25; // r8
  __int128 *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int128 *v30; // r9
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int128 *v34; // r9
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int128 *v40; // r9
  wchar_t *v41; // rax
  __int64 v42; // rax
  __int64 v43; // rdx
  __int128 *v44; // r9
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int128 *v48; // r9
  int v49; // ecx
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // rcx
  unsigned int v53; // ebx
  unsigned int SubInterfaceIndex; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v56; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v57; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v58; // [rsp+48h] [rbp-B8h]
  __int128 v59; // [rsp+58h] [rbp-A8h]
  __int64 v60; // [rsp+68h] [rbp-98h]
  int v61; // [rsp+70h] [rbp-90h]
  int v62; // [rsp+74h] [rbp-8Ch]
  __int128 v63; // [rsp+80h] [rbp-80h] BYREF
  __int128 v64; // [rsp+90h] [rbp-70h] BYREF
  __int128 v65; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v66[262]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v67[2]; // [rsp+1B6h] [rbp+B6h] BYREF
  wchar_t Str[128]; // [rsp+1B8h] [rbp+B8h] BYREF
  _DWORD v69[138]; // [rsp+2B8h] [rbp+1B8h] BYREF
  int v70; // [rsp+4E0h] [rbp+3E0h] BYREF
  __int128 v71; // [rsp+4E4h] [rbp+3E4h]
  __int128 v72; // [rsp+4F4h] [rbp+3F4h]
  int v73; // [rsp+504h] [rbp+404h]
  int v74; // [rsp+510h] [rbp+410h] BYREF
  unsigned int v75; // [rsp+514h] [rbp+414h]
  int v76; // [rsp+518h] [rbp+418h]
  int v77; // [rsp+51Ch] [rbp+41Ch]
  int v78; // [rsp+520h] [rbp+420h]
  int v79; // [rsp+524h] [rbp+424h]
  int v80; // [rsp+544h] [rbp+444h]
  unsigned int v81; // [rsp+75Ch] [rbp+65Ch]
  int v82; // [rsp+760h] [rbp+660h]
  int v83; // [rsp+764h] [rbp+664h]
  __int64 v84; // [rsp+76Ch] [rbp+66Ch]
  _BYTE v85[28]; // [rsp+774h] [rbp+674h]
  wchar_t pszDest[274]; // [rsp+790h] [rbp+690h] BYREF
  __int128 v87; // [rsp+9B4h] [rbp+8B4h]
  int v88; // [rsp+9D0h] [rbp+8D0h] BYREF
  _BYTE v89[2044]; // [rsp+9D4h] [rbp+8D4h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_9b65cff8e2b438daa92b03f64bab9903_Traceguids);
  }
  SubInterfaceIndex = 0;
  memset_0(v66, 0, 0x428u);
  v6 = *((_QWORD *)this + 7);
  v7 = *(_DWORD *)(v6 + 1472);
  LODWORD(v56) = 0;
  v65 = 0;
  v65 = *(_OWORD *)(v6 + 2120);
  v88 = 0;
  memset_0(v89, 0, sizeof(v89));
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v64 = 0;
  v58 = 0;
  v57 = 0;
  v59 = 0;
  v60 = 0;
  v8 = -1;
  v61 = -1;
  v62 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v57,
      L"IPv4Helper::ActivateRoute",
      &SubInterfaceIndex,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      (void *)v6);
  if ( v7 == 2 )
  {
    if ( *((_DWORD *)this + 19) )
    {
      if ( *((_DWORD *)this + 5) )
      {
        SubInterfaceIndex = IPv4Helper::AcquireIPAddressForClient(this, 0, (unsigned int *)this, a2, a3);
        if ( SubInterfaceIndex )
        {
          if ( (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v88) = 0;
            LOWORD(v70) = 0;
            v9 = *((_QWORD *)this + 7);
            if ( v9 && *(_QWORD *)(v9 + 16) )
              v10 = *(unsigned int *)(v9 + 16);
            else
              v10 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v70, v10);
            FormatRRASErrorString(
              &v88,
              L"Failed to Acquire IP address for the demand dial interface. Error:%d. Will continue using APIPA.",
              SubInterfaceIndex);
            if ( (byte_1800AA941 & 4) != 0 )
            {
              v11 = *((_QWORD *)this + 7);
              LODWORD(v12) = v11 + 2120;
              if ( !v11 )
                v12 = &v64;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceError,
                (unsigned int)&v88,
                (_DWORD)v12,
                (v11 + 2686) & -(__int64)(v11 != 0),
                (__int64)&v70);
            }
          }
          SubInterfaceIndex = 0;
        }
      }
    }
  }
  SubInterfaceIndex = (*((__int64 (__fastcall **)(_QWORD, __int64, __int64, _BYTE *))&xmmword_1800AA960 + 1))(
                        *(_QWORD *)(*((_QWORD *)this + 7) + 16LL),
                        2048,
                        1,
                        v66);
  if ( SubInterfaceIndex )
  {
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_144;
    LOWORD(v88) = 0;
    LOWORD(v70) = 0;
    v13 = *((_QWORD *)this + 7);
    if ( v13 && *(_QWORD *)(v13 + 16) )
      v8 = *(_DWORD *)(v13 + 16);
    ConvertPortNoToString(&v70, v8);
    FormatRRASErrorString(&v88, L"RasAllocateRoute failed: %d", SubInterfaceIndex);
    goto LABEL_27;
  }
  *((_DWORD *)this + 90) |= 4u;
  if ( v7 == 2 )
  {
    v16 = 0;
    *((_DWORD *)this + 85) = 0;
  }
  else if ( *((_DWORD *)this + 19) )
  {
    v16 = *((_DWORD *)this + 5);
    SubInterfaceIndex = IPv4Helper::GenerateSubInterfaceIndex(this);
    if ( SubInterfaceIndex )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_144;
      LOWORD(v88) = 0;
      LOWORD(v70) = 0;
      v22 = *((_QWORD *)this + 7);
      if ( v22 && *(_QWORD *)(v22 + 16) )
        v8 = *(_DWORD *)(v22 + 16);
      ConvertPortNoToString(&v70, v8);
      FormatRRASErrorString(&v88, L"GenerateSubInterfaceIndex failed: %d", SubInterfaceIndex);
      goto LABEL_27;
    }
  }
  else
  {
    v16 = *(_DWORD *)this;
    SubInterfaceIndex = RasAllocInterfaceLuidIndex(*(_QWORD *)(*((_QWORD *)this + 7) + 16LL), v69);
    if ( SubInterfaceIndex )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_144;
      LOWORD(v88) = 0;
      LOWORD(v70) = 0;
      v17 = *((_QWORD *)this + 7);
      if ( v17 && *(_QWORD *)(v17 + 16) )
        v8 = *(_DWORD *)(v17 + 16);
      ConvertPortNoToString(&v70, v8);
      FormatRRASErrorString(&v88, L"RasAllocInterfaceLuidIndex failed: %d", SubInterfaceIndex);
      goto LABEL_27;
    }
    *((_WORD *)this + 27) = 23;
    *((_QWORD *)this + 6) = *((_QWORD *)this + 6)
                          & 0xFFFF000000000000uLL
                          ^ ((unsigned __int64)v69[0] << 24)
                          & 0xFFFFFF000000LL;
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v88) = 0;
      LOWORD(v70) = 0;
      v18 = *((_QWORD *)this + 7);
      if ( v18 && *(_QWORD *)(v18 + 16) )
        v19 = *(unsigned int *)(v18 + 16);
      else
        v19 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v70, v19);
      FormatRRASErrorString(&v88, L"RasAllocInterfaceLuidIndex returns LuidIndex:%I64X", *((_QWORD *)this + 6));
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v20 = *((_QWORD *)this + 7);
        LODWORD(v21) = v20 + 2120;
        if ( !v20 )
          v21 = &v64;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v88,
          (_DWORD)v21,
          (v20 + 2686) & -(__int64)(v20 != 0),
          (__int64)&v70);
      }
    }
    *((_DWORD *)this + 90) |= 2u;
  }
  v69[133] = 0;
  v74 = 1200;
  if ( v7 == 2 )
  {
    v75 = 2;
    v23 = *(_DWORD *)this;
    v81 = *(_DWORD *)this;
    if ( *((_DWORD *)this + 19) )
      v23 = *((_DWORD *)this + 5);
    v83 = v23;
    v78 = *(_DWORD *)(*((_QWORD *)this + 7) + 1480LL);
  }
  else
  {
    v75 = *((_DWORD *)this + 19) == 0;
    v81 = v16;
    v78 = -1;
  }
  v82 = -1;
  v79 = *((_DWORD *)this + 85);
  v76 = 1;
  v77 = 1;
  v24 = *((_QWORD *)this + 7);
  v84 = *(_QWORD *)(v24 + 8);
  if ( *a2 )
  {
    v25 = a2;
LABEL_64:
    StringCchCopyW(pszDest, 0x111u, v25);
    goto LABEL_66;
  }
  v25 = (const wchar_t *)(v24 + 2686);
  if ( *v25 )
    goto LABEL_64;
  pszDest[0] = 0;
LABEL_66:
  v26 = (__int128 *)(*((_QWORD *)this + 7) + 2120LL);
  v87 = *v26;
  SubInterfaceIndex = NsiGetCompartmentIdForRoutingDomain(v26, &v56);
  if ( SubInterfaceIndex )
  {
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v88) = 0;
      LOWORD(v70) = 0;
      v27 = *((_QWORD *)this + 7);
      if ( v27 && *(_QWORD *)(v27 + 16) )
        v28 = *(unsigned int *)(v27 + 16);
      else
        v28 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v70, v28);
      FormatRRASErrorString(&v88, L"NsiGetCompartmentIdForRoutingDomain failed:%d", SubInterfaceIndex);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v29 = *((_QWORD *)this + 7);
        LODWORD(v30) = v29 + 2120;
        if ( !v29 )
          v30 = &v64;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v88,
          (_DWORD)v30,
          (v29 + 2686) & -(__int64)(v29 != 0),
          (__int64)&v70);
      }
    }
    SubInterfaceIndex = 0;
  }
  v80 = v56;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v88) = 0;
    LOWORD(v70) = 0;
    v31 = *((_QWORD *)this + 7);
    if ( v31 && *(_QWORD *)(v31 + 16) )
      v32 = *(unsigned int *)(v31 + 16);
    else
      v32 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v70, v32);
    FormatRRASErrorString(&v88, L"dwLocalAdd  0x%x", v81);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v33 = *((_QWORD *)this + 7);
      LODWORD(v34) = v33 + 2120;
      if ( !v33 )
        v34 = &v64;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceInfo,
        (unsigned int)&v88,
        (_DWORD)v34,
        (v33 + 2686) & -(__int64)(v33 != 0),
        (__int64)&v70);
    }
  }
  v35 = *((_QWORD *)this + 7);
  *(_OWORD *)v85 = *(_OWORD *)(v35 + 2136);
  *(_OWORD *)&v85[12] = *(_OWORD *)(v35 + 2148);
  SubInterfaceIndex = (*((__int64 (__fastcall **)(_QWORD, __int64, _BYTE *, int *))&xmmword_1800AA9B0 + 1))(
                        *(_QWORD *)(v35 + 16),
                        2048,
                        v66,
                        &v74);
  if ( SubInterfaceIndex )
  {
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_144;
    LOWORD(v88) = 0;
    LOWORD(v70) = 0;
    v36 = *((_QWORD *)this + 7);
    if ( v36 && *(_QWORD *)(v36 + 16) )
      v8 = *(_DWORD *)(v36 + 16);
    ConvertPortNoToString(&v70, v8);
    FormatRRASErrorString(&v88, L"RasActivateRoute failed: %d", SubInterfaceIndex);
    goto LABEL_27;
  }
  if ( v75 == 2 )
    *((_DWORD *)this + 84) = v69[0];
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v88) = 0;
    LOWORD(v70) = 0;
    v37 = *((_QWORD *)this + 7);
    if ( v37 && *(_QWORD *)(v37 + 16) )
      v38 = *(unsigned int *)(v37 + 16);
    else
      v38 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v70, v38);
    FormatRRASErrorString(&v88, L"AdapterName: %ws", v67);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v39 = *((_QWORD *)this + 7);
      LODWORD(v40) = v39 + 2120;
      if ( !v39 )
        v40 = &v64;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceInfo,
        (unsigned int)&v88,
        (_DWORD)v40,
        (v39 + 2686) & -(__int64)(v39 != 0),
        (__int64)&v70);
    }
  }
  v41 = wcschr(Str, 0x5Cu);
  if ( !v41 )
  {
    SubInterfaceIndex = 87;
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v70) = 0;
      v42 = *((_QWORD *)this + 7);
      if ( v42 && *(_QWORD *)(v42 + 16) )
        v8 = *(_DWORD *)(v42 + 16);
      ConvertPortNoToString(&v70, v8);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v43 = *((_QWORD *)this + 7);
        LODWORD(v44) = v43 + 2120;
        if ( !v43 )
          v44 = &v64;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Invalid AdapterName",
          (_DWORD)v44,
          (v43 + 2686) & -(__int64)(v43 != 0),
          (__int64)&v70);
      }
    }
    goto LABEL_144;
  }
  StringCchCopyW((STRSAFE_LPWSTR)this + 40, 0x80u, v41 + 1);
  if ( v7 != 2 && !*((_DWORD *)this + 19) )
    goto LABEL_144;
  v56 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v70) = 0;
    v45 = *((_QWORD *)this + 7);
    if ( v45 && *(_QWORD *)(v45 + 16) )
      v46 = *(unsigned int *)(v45 + 16);
    else
      v46 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v70, v46);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v47 = *((_QWORD *)this + 7);
      LODWORD(v48) = v47 + 2120;
      if ( !v47 )
        v48 = &v64;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceInfo,
        (unsigned int)L"Activate IPv4 Address for client...",
        (_DWORD)v48,
        (v47 + 2686) & -(__int64)(v47 != 0),
        (__int64)&v70);
    }
  }
  if ( v7 != 2 )
  {
    if ( *((_DWORD *)this + 19) )
    {
      v49 = 1;
      v56 = *((unsigned int *)this + 85);
      goto LABEL_131;
    }
LABEL_130:
    v49 = 0;
    if ( v7 == 2 )
      goto LABEL_144;
LABEL_131:
    if ( !*((_DWORD *)this + 19) && !v49 )
      goto LABEL_144;
    goto LABEL_133;
  }
  if ( !*((_DWORD *)this + 5) && !*(_DWORD *)this )
    goto LABEL_130;
  v56 = (*((_DWORD *)this + 84) & 0xFFFFFF | 0x17000000LL) << 24;
  *((_QWORD *)this + 6) = v56;
  if ( !*((_DWORD *)this + 19) )
    goto LABEL_144;
LABEL_133:
  v63 = v65;
  SubInterfaceIndex = (*(__int64 (__fastcall **)(__int128 *, _QWORD, _QWORD, __int64 *))(*((_QWORD *)this + 43) + 72LL))(
                        &v63,
                        *((unsigned int *)this + 5),
                        v75,
                        &v56);
  if ( SubInterfaceIndex )
  {
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_144;
    LOWORD(v88) = 0;
    LOWORD(v70) = 0;
    v50 = *((_QWORD *)this + 7);
    if ( v50 && *(_QWORD *)(v50 + 16) )
      v8 = *(_DWORD *)(v50 + 16);
    ConvertPortNoToString(&v70, v8);
    FormatRRASErrorString(&v88, L"IPCP: Activate Ipv4 Address for client done %d", SubInterfaceIndex);
LABEL_27:
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v14 = *((_QWORD *)this + 7);
      LODWORD(v15) = v14 + 2120;
      if ( !v14 )
        v15 = &v64;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceError,
        (unsigned int)&v88,
        (_DWORD)v15,
        (v14 + 2686) & -(__int64)(*((_QWORD *)this + 7) != 0),
        (__int64)&v70);
    }
    goto LABEL_144;
  }
  if ( v7 == 2 )
  {
    if ( *((_DWORD *)this + 19) )
    {
      v51 = *(unsigned int *)this;
      if ( (_DWORD)v51 )
      {
        v52 = *((unsigned int *)this + 5);
        if ( (_DWORD)v52 )
          (*(void (__fastcall **)(__int64, __int64, __int64 *, _QWORD, __int128 *))(*((_QWORD *)this + 43) + 168LL))(
            v52,
            v51,
            &v56,
            0,
            &v65);
      }
    }
  }
LABEL_144:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      WPP_9b65cff8e2b438daa92b03f64bab9903_Traceguids,
      SubInterfaceIndex);
  }
  v53 = SubInterfaceIndex;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v57);
  return v53;
}

```

## disassembly

```asm
0x180048b5c  mov     [rsp-8+arg_18], rbx
0x180048b61  push    rbp
0x180048b62  push    rsi
0x180048b63  push    rdi
0x180048b64  push    r12
0x180048b66  push    r13
0x180048b68  push    r14
0x180048b6a  push    r15
0x180048b6c  lea     rbp, [rsp-10E0h]
0x180048b74  mov     eax, 11E0h
0x180048b79  call    _alloca_probe
0x180048b7e  sub     rsp, rax
0x180048b81  mov     rax, cs:__security_cookie
0x180048b88  xor     rax, rsp
0x180048b8b  mov     [rbp+1110h+var_40], rax
0x180048b92  mov     r14, r8
0x180048b95  mov     r15, rdx
0x180048b98  mov     rbx, rcx
0x180048b9b  lea     rax, WPP_GLOBAL_Control
0x180048ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x180048ba9  cmp     rcx, rax
0x180048bac  jz      short loc_180048BCF
0x180048bae  test    byte ptr [rcx+1Ch], 1
0x180048bb2  jz      short loc_180048BCF
0x180048bb4  cmp     byte ptr [rcx+19h], 6
0x180048bb8  jb      short loc_180048BCF
0x180048bba  mov     edx, 17h
0x180048bbf  lea     r8, WPP_9b65cff8e2b438daa92b03f64bab9903_Traceguids
0x180048bc6  mov     rcx, [rcx+10h]
0x180048bca  call    WPP_SF_
0x180048bcf  xor     r13d, r13d
0x180048bd2  mov     [rsp+1210h+var_11E0], r13d
0x180048bd7  xor     edx, edx; Val
0x180048bd9  mov     r8d, 428h; Size
0x180048bdf  lea     rcx, [rbp+1110h+var_1160]; void *
0x180048be3  call    memset_0
0x180048be8  mov     rsi, [rbx+38h]
0x180048bec  mov     r12d, [rsi+5C0h]
0x180048bf3  mov     dword ptr [rsp+1210h+var_11D8], r13d
0x180048bf8  xorps   xmm0, xmm0
0x180048bfb  movups  [rbp+1110h+var_1170], xmm0
0x180048bff  movups  xmm1, xmmword ptr [rsi+848h]
0x180048c06  movdqu  [rbp+1110h+var_1170], xmm1
0x180048c0b  mov     [rbp+1110h+var_840], r13d
0x180048c12  xor     edx, edx; Val
0x180048c14  mov     r8d, 7FCh; Size
0x180048c1a  lea     rcx, [rbp+1110h+var_83C]; void *
0x180048c21  call    memset_0
0x180048c26  mov     [rbp+1110h+var_D30], r13d
0x180048c2d  xorps   xmm0, xmm0
0x180048c30  xor     eax, eax
0x180048c32  movups  [rbp+1110h+var_D2C], xmm0
0x180048c39  movups  [rbp+1110h+var_D1C], xmm0
0x180048c40  mov     [rbp+1110h+var_D0C], eax
0x180048c46  movups  [rbp+1110h+var_1180], xmm0
0x180048c4a  xorps   xmm1, xmm1
0x180048c4d  movdqu  [rsp+1210h+var_11C8], xmm1
0x180048c53  mov     [rsp+1210h+var_11D0], r13
0x180048c58  movdqu  [rsp+1210h+var_11B8], xmm0
0x180048c5e  mov     [rsp+1210h+var_11A8], r13
0x180048c63  or      edi, 0FFFFFFFFh
0x180048c66  mov     [rsp+1210h+var_11A0], edi
0x180048c6a  mov     [rsp+1210h+var_119C], r13d
0x180048c6f  test    cs:byte_1800AA941, 8
0x180048c76  jz      short loc_180048C9A
0x180048c78  mov     [rsp+1210h+var_11F0], rsi; void *
0x180048c7d  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180048c84  lea     r8, [rsp+1210h+var_11E0]; unsigned int *
0x180048c89  lea     rdx, aIpv4helperActi; "IPv4Helper::ActivateRoute"
0x180048c90  lea     rcx, [rsp+1210h+var_11D0]; this
0x180048c95  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x180048c9a  cmp     r12d, 2
0x180048c9e  jnz     loc_180048D90
0x180048ca4  cmp     [rbx+4Ch], r13d
0x180048ca8  jz      loc_180048D90
0x180048cae  cmp     [rbx+14h], r13d
0x180048cb2  jz      loc_180048D90
0x180048cb8  mov     [rsp+1210h+var_11F0], r14; unsigned __int16 *
0x180048cbd  mov     r9, r15; unsigned __int16 *
0x180048cc0  mov     r8, rbx; unsigned int *
0x180048cc3  xor     edx, edx; unsigned int
0x180048cc5  mov     rcx, rbx; this
0x180048cc8  call    ?AcquireIPAddressForClient@IPv4Helper@@QEAAKKPEAKPEAG1@Z; IPv4Helper::AcquireIPAddressForClient(ulong,ulong *,ushort *,ushort *)
0x180048ccd  mov     [rsp+1210h+var_11E0], eax
0x180048cd1  test    eax, eax
0x180048cd3  jz      loc_180048D90
0x180048cd9  test    cs:byte_1800AA941, 4
0x180048ce0  jz      loc_180048D8B
0x180048ce6  mov     word ptr [rbp+1110h+var_840], r13w
0x180048cee  mov     word ptr [rbp+1110h+var_D30], r13w
0x180048cf6  mov     rax, [rbx+38h]
0x180048cfa  test    rax, rax
0x180048cfd  jz      short loc_180048D0A
0x180048cff  cmp     [rax+10h], r13
0x180048d03  jz      short loc_180048D0A
0x180048d05  mov     edx, [rax+10h]
0x180048d08  jmp     short loc_180048D0C
0x180048d0a  mov     edx, edi
0x180048d0c  lea     rcx, [rbp+1110h+var_D30]
0x180048d13  call    ConvertPortNoToString
0x180048d18  mov     r8d, [rsp+1210h+var_11E0]
0x180048d1d  lea     rdx, aFailedToAcquir_0; "Failed to Acquire IP address for the de"...
0x180048d24  lea     rcx, [rbp+1110h+var_840]
0x180048d2b  call    FormatRRASErrorString
0x180048d30  test    cs:byte_1800AA941, 4
0x180048d37  jz      short loc_180048D8B
0x180048d39  mov     rdx, [rbx+38h]
0x180048d3d  mov     rax, rdx
0x180048d40  lea     rcx, [rdx+0A7Eh]
0x180048d47  neg     rax
0x180048d4a  sbb     r8, r8
0x180048d4d  and     r8, rcx
0x180048d50  test    rdx, rdx
0x180048d53  lea     r9, [rdx+848h]
0x180048d5a  jnz     short loc_180048D60
0x180048d5c  lea     r9, [rbp+1110h+var_1180]
0x180048d60  lea     rax, [rbp+1110h+var_D30]
0x180048d67  mov     [rsp+1210h+var_11E8], rax
0x180048d6c  mov     [rsp+1210h+var_11F0], r8
0x180048d71  lea     r8, [rbp+1110h+var_840]
0x180048d78  lea     rdx, RasVpnIkeParamTraceError
0x180048d7f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180048d86  call    McTemplateU0zjzz_EventWriteTransfer
0x180048d8b  mov     [rsp+1210h+var_11E0], r13d
0x180048d90  mov     rcx, [rbx+38h]
0x180048d94  lea     r9, [rbp+1110h+var_1160]
0x180048d98  mov     edx, 800h
0x180048d9d  mov     r8d, 1
0x180048da3  mov     rcx, [rcx+10h]
0x180048da7  mov     rax, qword ptr cs:xmmword_1800AA960+8
0x180048dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048db3  mov     [rsp+1210h+var_11E0], eax
0x180048db7  test    eax, eax
0x180048db9  jz      loc_180048E78
0x180048dbf  test    cs:byte_1800AA941, 4
0x180048dc6  jz      loc_1800496A1
0x180048dcc  mov     word ptr [rbp+1110h+var_840], r13w
0x180048dd4  mov     word ptr [rbp+1110h+var_D30], r13w
0x180048ddc  mov     rax, [rbx+38h]
0x180048de0  test    rax, rax
0x180048de3  jz      short loc_180048DEE
0x180048de5  cmp     [rax+10h], r13
0x180048de9  jz      short loc_180048DEE
0x180048deb  mov     edi, [rax+10h]
0x180048dee  mov     edx, edi
0x180048df0  lea     rcx, [rbp+1110h+var_D30]
0x180048df7  call    ConvertPortNoToString
0x180048dfc  lea     rdx, aRasallocaterou; "RasAllocateRoute failed: %d"
0x180048e03  mov     r8d, [rsp+1210h+var_11E0]
0x180048e08  lea     rcx, [rbp+1110h+var_840]
0x180048e0f  call    FormatRRASErrorString
0x180048e14  test    cs:byte_1800AA941, 4
0x180048e1b  jz      loc_1800496A1
0x180048e21  mov     rdx, [rbx+38h]
0x180048e25  mov     rax, rdx
0x180048e28  neg     rax
0x180048e2b  lea     rcx, [rdx+0A7Eh]
0x180048e32  sbb     r8, r8
0x180048e35  and     r8, rcx
0x180048e38  lea     r9, [rdx+848h]
0x180048e3f  test    rdx, rdx
0x180048e42  jnz     short loc_180048E48
0x180048e44  lea     r9, [rbp+1110h+var_1180]
0x180048e48  lea     rax, [rbp+1110h+var_D30]
0x180048e4f  mov     [rsp+1210h+var_11E8], rax
0x180048e54  mov     [rsp+1210h+var_11F0], r8
0x180048e59  lea     r8, [rbp+1110h+var_840]
0x180048e60  lea     rdx, RasVpnIkeParamTraceError
0x180048e67  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180048e6e  call    McTemplateU0zjzz_EventWriteTransfer
0x180048e73  jmp     loc_1800496A1
0x180048e78  or      dword ptr [rbx+168h], 4
0x180048e7f  mov     r14d, 2
0x180048e85  cmp     r12d, r14d
0x180048e88  jz      loc_18004904B
0x180048e8e  cmp     [rbx+4Ch], r13d
0x180048e92  jnz     loc_180048FEF
0x180048e98  mov     esi, [rbx]
0x180048e9a  mov     rcx, [rbx+38h]
0x180048e9e  lea     rdx, [rbp+1110h+var_F58]
0x180048ea5  mov     rcx, [rcx+10h]
0x180048ea9  call    cs:__imp_RasAllocInterfaceLuidIndex
0x180048eaf  mov     [rsp+1210h+var_11E0], eax
0x180048eb3  test    eax, eax
0x180048eb5  jz      short loc_180048F00
0x180048eb7  test    cs:byte_1800AA941, 4
0x180048ebe  jz      loc_1800496A1
0x180048ec4  mov     word ptr [rbp+1110h+var_840], r13w
0x180048ecc  mov     word ptr [rbp+1110h+var_D30], r13w
0x180048ed4  mov     rax, [rbx+38h]
0x180048ed8  test    rax, rax
0x180048edb  jz      short loc_180048EE6
0x180048edd  cmp     [rax+10h], r13
0x180048ee1  jz      short loc_180048EE6
0x180048ee3  mov     edi, [rax+10h]
0x180048ee6  mov     edx, edi
0x180048ee8  lea     rcx, [rbp+1110h+var_D30]
0x180048eef  call    ConvertPortNoToString
0x180048ef4  lea     rdx, aRasallocinterf; "RasAllocInterfaceLuidIndex failed: %d"
0x180048efb  jmp     loc_180048E03
0x180048f00  mov     word ptr [rbx+36h], 17h
0x180048f06  mov     ecx, [rbp+1110h+var_F58]
0x180048f0c  shl     rcx, 18h
0x180048f10  mov     rax, 0FFFFFF000000h
0x180048f1a  and     rcx, rax
0x180048f1d  mov     rax, [rbx+30h]
0x180048f21  mov     rdx, 0FFFF000000000000h
0x180048f2b  and     rax, rdx
0x180048f2e  xor     rcx, rax
0x180048f31  mov     [rbx+30h], rcx
0x180048f35  test    cs:byte_1800AA941, 8
0x180048f3c  jz      loc_180048FE6
0x180048f42  mov     word ptr [rbp+1110h+var_840], r13w
0x180048f4a  mov     word ptr [rbp+1110h+var_D30], r13w
0x180048f52  mov     rax, [rbx+38h]
0x180048f56  test    rax, rax
0x180048f59  jz      short loc_180048F66
0x180048f5b  cmp     [rax+10h], r13
0x180048f5f  jz      short loc_180048F66
0x180048f61  mov     edx, [rax+10h]
0x180048f64  jmp     short loc_180048F68
0x180048f66  mov     edx, edi
0x180048f68  lea     rcx, [rbp+1110h+var_D30]
0x180048f6f  call    ConvertPortNoToString
0x180048f74  mov     r8, [rbx+30h]
0x180048f78  lea     rdx, aRasallocinterf_0; "RasAllocInterfaceLuidIndex returns Luid"...
0x180048f7f  lea     rcx, [rbp+1110h+var_840]
0x180048f86  call    FormatRRASErrorString
0x180048f8b  test    cs:byte_1800AA941, 8
0x180048f92  jz      short loc_180048FE6
0x180048f94  mov     rdx, [rbx+38h]
0x180048f98  mov     rax, rdx
0x180048f9b  lea     rcx, [rdx+0A7Eh]
0x180048fa2  neg     rax
0x180048fa5  sbb     r8, r8
0x180048fa8  and     r8, rcx
0x180048fab  test    rdx, rdx
0x180048fae  lea     r9, [rdx+848h]
0x180048fb5  jnz     short loc_180048FBB
0x180048fb7  lea     r9, [rbp+1110h+var_1180]
0x180048fbb  lea     rax, [rbp+1110h+var_D30]
0x180048fc2  mov     [rsp+1210h+var_11E8], rax
0x180048fc7  mov     [rsp+1210h+var_11F0], r8
0x180048fcc  lea     r8, [rbp+1110h+var_840]
0x180048fd3  lea     rdx, RasVpnIkeParamTraceInfo
0x180048fda  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180048fe1  call    McTemplateU0zjzz_EventWriteTransfer
0x180048fe6  or      [rbx+168h], r14d
0x180048fed  jmp     short loc_180049055
0x180048fef  mov     esi, [rbx+14h]
0x180048ff2  mov     rcx, rbx; this
0x180048ff5  call    ?GenerateSubInterfaceIndex@IPv4Helper@@QEAAKXZ; IPv4Helper::GenerateSubInterfaceIndex(void)
0x180048ffa  mov     [rsp+1210h+var_11E0], eax
0x180048ffe  test    eax, eax
0x180049000  jz      short loc_180049055
0x180049002  test    cs:byte_1800AA941, 4
0x180049009  jz      loc_1800496A1
0x18004900f  mov     word ptr [rbp+1110h+var_840], r13w
0x180049017  mov     word ptr [rbp+1110h+var_D30], r13w
0x18004901f  mov     rax, [rbx+38h]
0x180049023  test    rax, rax
0x180049026  jz      short loc_180049031
0x180049028  cmp     [rax+10h], r13
0x18004902c  jz      short loc_180049031
0x18004902e  mov     edi, [rax+10h]
0x180049031  mov     edx, edi
0x180049033  lea     rcx, [rbp+1110h+var_D30]
0x18004903a  call    ConvertPortNoToString
0x18004903f  lea     rdx, aGeneratesubint; "GenerateSubInterfaceIndex failed: %d"
0x180049046  jmp     loc_180048E03
0x18004904b  mov     esi, r13d
0x18004904e  mov     [rbx+154h], r13d
0x180049055  mov     [rbp+1110h+var_D44], r13d
0x18004905c  mov     [rbp+1110h+var_D00], 4B0h
0x180049066  cmp     r12d, r14d
0x180049069  jnz     short loc_18004909B
0x18004906b  mov     [rbp+1110h+var_CFC], r14d
0x180049072  mov     eax, [rbx]
0x180049074  mov     [rbp+1110h+var_AB4], eax
0x18004907a  cmp     [rbx+4Ch], r13d
0x18004907e  jz      short loc_180049083
0x180049080  mov     eax, [rbx+14h]
0x180049083  mov     [rbp+1110h+var_AAC], eax
0x180049089  mov     rax, [rbx+38h]
0x18004908d  mov     ecx, [rax+5C8h]
0x180049093  mov     [rbp+1110h+var_CF0], ecx
0x180049099  jmp     short loc_1800490B7
0x18004909b  mov     eax, r13d
0x18004909e  cmp     [rbx+4Ch], r13d
0x1800490a2  setz    al
0x1800490a5  mov     [rbp+1110h+var_CFC], eax
0x1800490ab  mov     [rbp+1110h+var_AB4], esi
0x1800490b1  mov     [rbp+1110h+var_CF0], edi
0x1800490b7  mov     [rbp+1110h+var_AB0], edi
0x1800490bd  mov     eax, [rbx+154h]
0x1800490c3  mov     [rbp+1110h+var_CEC], eax
0x1800490c9  mov     eax, 1
0x1800490ce  mov     [rbp+1110h+var_CF8], eax
0x1800490d4  mov     [rbp+1110h+var_CF4], eax
0x1800490da  mov     r8, [rbx+38h]
  ... truncated ...
```
