# VPNIKEConnection::CreateTunnel(_IKETUNNEL_PARAMETERS_ &,_VPN_DPD_CONFIG_ *)

- ea: `0x18000d620`
- end: `0x18000e01b`
- name: `?CreateTunnel@VPNIKEConnection@@UEAAKAEAU_IKETUNNEL_PARAMETERS_@@PEAU_VPN_DPD_CONFIG_@@@Z`
- size: `2555`
- prototype: `__int64 __fastcall(VPNIKEConnection *this, struct _IKETUNNEL_PARAMETERS_ *, struct _VPN_DPD_CONFIG_ *)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800170a0`
- `0x1800221b0`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x1800078d4`
- `0x18000d620`
- `0x18001287c`
- `0x1800131c8`
- `0x180014714`
- `0x180014ce0`
- `0x18002ed60`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## string_xrefs

- `0x18000d71c`: `VPNIKEConnection::CreateTunnel`
- `0x18000d8af`: `Create tunnel called without Cfg processing. Hence erroring out.`
- `0x18000d979`: `CreateTunnel called in invalid state. Hence erroring out.`
- `0x18000dcbe`: `VPNIKEIOCTLHelper::CreateTunnel failed: %d`
- `0x18000ddc8`: `CreateTunnel: IsRouter(%d), InterfaceInfo.dwDpdTimeout(%d), InterfaceInfo.dwIkeResponseTimeout(%d), NetworkTimeOut(%d)`
- `0x18000defb`: `DPD configuration: dpdRequired(%d), dpdTimePeriod(%d), dpdResponseTimeout(%d)`

## pseudocode

```c
__int64 __fastcall VPNIKEConnection::CreateTunnel(
        VPNIKEConnection *this,
        struct _IKETUNNEL_PARAMETERS_ *a2,
        struct _VPN_DPD_CONFIG_ *a3)
{
  PVOID *v6; // rbx
  unsigned int v7; // r14d
  char v8; // al
  int v9; // edx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int128 *v12; // r9
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int128 *v16; // r9
  __int64 v17; // rax
  __int64 v18; // rdx
  __int128 *v19; // r9
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int128 *v23; // r9
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int128 *v27; // r9
  __int64 v28; // rcx
  __int64 v29; // rdx
  char *v30; // r9
  __int64 v31; // r8
  __int64 v32; // rax
  __int64 v33; // rdx
  __int128 *v34; // r9
  __int64 v35; // rax
  __int64 v36; // rdx
  _DWORD *v37; // r9
  __int64 v38; // rdx
  __int128 *v39; // r9
  int v40; // ecx
  _DWORD *v41; // rdx
  int v42; // eax
  unsigned int *v43; // rsi
  int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // edx
  __int64 v47; // rax
  __int64 v48; // rdx
  __int128 *v49; // r9
  unsigned int v50; // ebx
  void *v52; // [rsp+20h] [rbp-E0h]
  __int64 v53; // [rsp+28h] [rbp-D8h]
  unsigned int v54; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v55; // [rsp+68h] [rbp-98h] BYREF
  __int128 v56; // [rsp+70h] [rbp-90h]
  __int128 v57; // [rsp+80h] [rbp-80h]
  __int64 v58; // [rsp+90h] [rbp-70h]
  int v59; // [rsp+98h] [rbp-68h]
  int v60; // [rsp+9Ch] [rbp-64h]
  __int128 v61; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v62[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v63; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v64; // [rsp+D4h] [rbp-2Ch]
  __int128 v65; // [rsp+E4h] [rbp-1Ch]
  int v66; // [rsp+F4h] [rbp-Ch]
  int v67; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v68[2044]; // [rsp+104h] [rbp+4h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_dc(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids,
      *((unsigned int *)this + 38),
      *((_BYTE *)this + 16) != 0);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v54 = 0;
  v67 = 0;
  memset_0(v68, 0, sizeof(v68));
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v61 = 0;
  v56 = 0;
  v55 = 0;
  v57 = 0;
  v58 = 0;
  v7 = -1;
  v59 = -1;
  v60 = 0;
  v8 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v55,
      L"VPNIKEConnection::CreateTunnel",
      &v54,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      *((void **)this + 14));
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v8 = byte_1800AA941;
  }
  v9 = *((_DWORD *)this + 38);
  if ( (v9 & 0x100000) != 0 )
  {
    v54 = 617;
    if ( (v8 & 4) != 0 )
    {
      LOWORD(v63) = 0;
      v10 = *((_QWORD *)this + 14);
      if ( v10 && *(_QWORD *)(v10 + 16) )
        v7 = *(_DWORD *)(v10 + 16);
      ConvertPortNoToString(&v63, v7);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v11 = *((_QWORD *)this + 14);
        LODWORD(v12) = v11 + 2120;
        if ( !v11 )
          v12 = &v61;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Disconnect triggered on this connection. Hence exit.",
          (_DWORD)v12,
          (v11 + 2686) & -(__int64)(v11 != 0),
          (__int64)&v63);
      }
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      {
        v13 = 58;
LABEL_21:
        WPP_SF_d(v6[2], v13, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, v54);
LABEL_130:
        v6 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_131;
      }
      goto LABEL_131;
    }
  }
  else if ( (v9 & 0x10) != 0 || (v14 = *((_QWORD *)this + 14), *(_DWORD *)(v14 + 1472) == 2) )
  {
    if ( (v9 & 0x20) != 0 )
    {
      if ( *(_DWORD *)(*((_QWORD *)this + 14) + 4252LL) == 1 )
        VPNIKEConnection::RegisterForLowPowerModeNetEvent(this);
      VPNIKEConnection::UpdateConnectionState(this, 4u);
      VPNIKEConnection::UpdateVPNIKETunnelParams(this, a2);
      if ( *((_BYTE *)this + 264) && *((_BYTE *)this + 265) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
        }
        memset((char *)v62 + 2, 0, 26);
        if ( *((_BYTE *)this + 16) )
        {
          LOWORD(v62[0]) = 2;
          DWORD1(v62[0]) = *((_DWORD *)this + 12);
        }
        else
        {
          LOWORD(v62[0]) = 23;
          *(_OWORD *)((char *)v62 + 8) = *(_OWORD *)((char *)this + 52);
        }
        v54 = (***((__int64 (__fastcall ****)(_QWORD, char *, _OWORD *, _QWORD))this + 29))(
                *((_QWORD *)this + 29),
                (char *)this + 8,
                v62,
                *((unsigned int *)this + 27));
        if ( v54 )
        {
          if ( (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v67) = 0;
            LOWORD(v63) = 0;
            v20 = *((_QWORD *)this + 14);
            if ( v20 && *(_QWORD *)(v20 + 16) )
              v21 = *(unsigned int *)(v20 + 16);
            else
              v21 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v63, v21);
            FormatRRASErrorString(&v67, L"AddOrModifyIPAddressChangeForConnection failed: %d", v54);
            if ( (byte_1800AA941 & 4) != 0 )
            {
              v22 = *((_QWORD *)this + 14);
              LODWORD(v23) = v22 + 2120;
              if ( !v22 )
                v23 = &v61;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceError,
                (unsigned int)&v67,
                (_DWORD)v23,
                (v22 + 2686) & -(__int64)(v22 != 0),
                (__int64)&v63);
            }
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, v54);
          }
          v54 = 0;
        }
      }
      else if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v63) = 0;
        v24 = *((_QWORD *)this + 14);
        if ( v24 && *(_QWORD *)(v24 + 16) )
          v25 = *(unsigned int *)(v24 + 16);
        else
          v25 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v63, v25);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v26 = *((_QWORD *)this + 14);
          LODWORD(v27) = v26 + 2120;
          if ( !v26 )
            v27 = &v61;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"mobike is NOT enabled",
            (_DWORD)v27,
            (v26 + 2686) & -(__int64)(v26 != 0),
            (__int64)&v63);
        }
      }
      BFEHandler::GetQMEncryption(*((BFEHandler **)this + 26), (unsigned int *)this + 67);
      v28 = *((_QWORD *)this + 30);
      v29 = *((_QWORD *)this + 14);
      v62[0] = *(_OWORD *)(v29 + 44);
      v30 = (char *)this + 72;
      LOBYTE(v31) = *(_DWORD *)(v29 + 40) == 2;
      LOBYTE(v30) = *((_BYTE *)this + 16);
      v54 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, char *, _DWORD, char *, char *, char *, char *, _OWORD *))(*(_QWORD *)v28 + 8LL))(
              v28,
              *((_QWORD *)this + 1),
              v31,
              v30,
              *((_DWORD *)this + 27),
              (char *)this + 48,
              (char *)this + 68,
              (char *)this + 52,
              (char *)this + 72,
              v62);
      if ( v54 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v67) = 0;
          LOWORD(v63) = 0;
          v32 = *((_QWORD *)this + 14);
          if ( v32 && *(_QWORD *)(v32 + 16) )
            v7 = *(_DWORD *)(v32 + 16);
          ConvertPortNoToString(&v63, v7);
          FormatRRASErrorString(&v67, L"VPNIKEIOCTLHelper::CreateTunnel failed: %d", v54);
          if ( (byte_1800AA941 & 4) != 0 )
          {
            v33 = *((_QWORD *)this + 14);
            LODWORD(v34) = v33 + 2120;
            if ( !v33 )
              v34 = &v61;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v67,
              (_DWORD)v34,
              (v33 + 2686) & -(__int64)(v33 != 0),
              (__int64)&v63);
          }
        }
        v6 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v13 = 63;
            goto LABEL_21;
          }
          goto LABEL_131;
        }
      }
      else
      {
        if ( !a3 )
          goto LABEL_130;
        if ( (byte_1800AA941 & 8) != 0 )
        {
          LOWORD(v67) = 0;
          LOWORD(v63) = 0;
          v35 = *((_QWORD *)this + 14);
          if ( v35 && *(_QWORD *)(v35 + 16) )
            v36 = *(unsigned int *)(v35 + 16);
          else
            v36 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v63, v36);
          v37 = (_DWORD *)*((_QWORD *)this + 14);
          LODWORD(v53) = v37[88];
          LODWORD(v52) = v37[507];
          FormatRRASErrorString(
            &v67,
            L"CreateTunnel: IsRouter(%d), InterfaceInfo.dwDpdTimeout(%d), InterfaceInfo.dwIkeResponseTimeout(%d), NetworkTimeOut(%d)",
            v37[368] == 2,
            (unsigned int)v37[506],
            v52,
            v53);
          if ( (byte_1800AA941 & 8) != 0 )
          {
            v38 = *((_QWORD *)this + 14);
            LODWORD(v39) = v38 + 2120;
            if ( !v38 )
              v39 = &v61;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceInfo,
              (unsigned int)&v67,
              (_DWORD)v39,
              (v38 + 2686) & -(__int64)(v38 != 0),
              (__int64)&v63);
          }
        }
        v40 = *(_DWORD *)(*((_QWORD *)this + 14) + 1472LL);
        *(_DWORD *)a3 = 1;
        v41 = (_DWORD *)*((_QWORD *)this + 14);
        v42 = v41[506];
        if ( v40 == 2 || v42 && v41[507] )
        {
          v43 = (unsigned int *)((char *)a3 + 4);
          *((_DWORD *)a3 + 1) = v42;
          v44 = *(_DWORD *)(*((_QWORD *)this + 14) + 2028LL);
        }
        else
        {
          v45 = v41[88];
          v43 = (unsigned int *)((char *)a3 + 4);
          if ( v45 )
          {
            if ( v45 >= 3 )
            {
              v46 = 2 * v45 / 3;
              *v43 = v46;
              v44 = *(_DWORD *)(*((_QWORD *)this + 14) + 352LL) - v46;
            }
            else
            {
              *v43 = 2;
              v44 = 1;
            }
          }
          else
          {
            *v43 = 10;
            v44 = 5;
          }
        }
        *((_DWORD *)a3 + 2) = v44;
        if ( (byte_1800AA941 & 8) != 0 )
        {
          LOWORD(v67) = 0;
          LOWORD(v63) = 0;
          v47 = *((_QWORD *)this + 14);
          if ( v47 && *(_QWORD *)(v47 + 16) )
            v7 = *(_DWORD *)(v47 + 16);
          ConvertPortNoToString(&v63, v7);
          LODWORD(v52) = *((_DWORD *)a3 + 2);
          FormatRRASErrorString(
            &v67,
            L"DPD configuration: dpdRequired(%d), dpdTimePeriod(%d), dpdResponseTimeout(%d)",
            *(unsigned int *)a3,
            *v43,
            v52);
          if ( (byte_1800AA941 & 8) != 0 )
          {
            v48 = *((_QWORD *)this + 14);
            LODWORD(v49) = v48 + 2120;
            if ( !v48 )
              v49 = &v61;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceInfo,
              (unsigned int)&v67,
              (_DWORD)v49,
              (v48 + 2686) & -(__int64)(v48 != 0),
              (__int64)&v63);
          }
        }
        v6 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_ddd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              64,
              &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids,
              *(unsigned int *)a3,
              *v43,
              *((_DWORD *)a3 + 2));
            goto LABEL_130;
          }
          goto LABEL_131;
        }
      }
    }
    else
    {
      v54 = 4317;
      if ( (v8 & 4) != 0 )
      {
        LOWORD(v63) = 0;
        v17 = *((_QWORD *)this + 14);
        if ( v17 && *(_QWORD *)(v17 + 16) )
          v7 = *(_DWORD *)(v17 + 16);
        ConvertPortNoToString(&v63, v7);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v18 = *((_QWORD *)this + 14);
          LODWORD(v19) = v18 + 2120;
          if ( !v18 )
            v19 = &v61;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)L"CreateTunnel called in invalid state. Hence erroring out.",
            (_DWORD)v19,
            (v18 + 2686) & -(__int64)(v18 != 0),
            (__int64)&v63);
        }
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
        {
          v13 = 60;
          goto LABEL_21;
        }
        goto LABEL_131;
      }
    }
  }
  else
  {
    v54 = 13900;
    if ( (v8 & 4) != 0 )
    {
      LOWORD(v63) = 0;
      if ( v14 && *(_QWORD *)(v14 + 16) )
        v7 = *(_DWORD *)(v14 + 16);
      ConvertPortNoToString(&v63, v7);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v15 = *((_QWORD *)this + 14);
        LODWORD(v16) = v15 + 2120;
        if ( !v15 )
          v16 = &v61;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Create tunnel called without Cfg processing. Hence erroring out.",
          (_DWORD)v16,
          (v15 + 2686) & -(__int64)(v15 != 0),
          (__int64)&v63);
      }
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      {
        v13 = 59;
        goto LABEL_21;
      }
LABEL_131:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 6u )
        WPP_SF_d(v6[2], 65, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, v54);
    }
  }
  v50 = v54;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v55);
  return v50;
}

```

## disassembly

```asm
0x18000d620  mov     [rsp-8+arg_18], rbx
0x18000d625  push    rbp
0x18000d626  push    rsi
0x18000d627  push    rdi
0x18000d628  push    r12
0x18000d62a  push    r13
0x18000d62c  push    r14
0x18000d62e  push    r15
0x18000d630  lea     rbp, [rsp-810h]
0x18000d638  sub     rsp, 910h
0x18000d63f  mov     rax, cs:__security_cookie
0x18000d646  xor     rax, rsp
0x18000d649  mov     [rbp+840h+var_40], rax
0x18000d650  mov     r12, r8
0x18000d653  mov     rsi, rdx
0x18000d656  mov     rdi, rcx
0x18000d659  lea     rax, WPP_GLOBAL_Control
0x18000d660  xor     r13d, r13d
0x18000d663  mov     rbx, cs:WPP_GLOBAL_Control
0x18000d66a  cmp     rbx, rax
0x18000d66d  jz      short loc_18000D6A8
0x18000d66f  test    byte ptr [rbx+1Ch], 1
0x18000d673  jz      short loc_18000D6A8
0x18000d675  cmp     byte ptr [rbx+19h], 6
0x18000d679  jb      short loc_18000D6A8
0x18000d67b  cmp     [rcx+10h], r13b
0x18000d67f  setnz   al
0x18000d682  lea     edx, [r13+39h]
0x18000d686  mov     byte ptr [rsp+940h+var_920], al
0x18000d68a  mov     r9d, [rcx+98h]
0x18000d691  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18000d698  mov     rcx, [rbx+10h]
0x18000d69c  call    WPP_SF_dc
0x18000d6a1  mov     rbx, cs:WPP_GLOBAL_Control
0x18000d6a8  mov     [rsp+940h+var_8E0], r13d
0x18000d6ad  mov     [rbp+840h+var_840], r13d
0x18000d6b1  xor     edx, edx; Val
0x18000d6b3  mov     r8d, 7FCh; Size
0x18000d6b9  lea     rcx, [rbp+840h+var_83C]; void *
0x18000d6bd  call    memset_0
0x18000d6c2  mov     [rbp+840h+var_870], r13d
0x18000d6c6  xorps   xmm0, xmm0
0x18000d6c9  xor     eax, eax
0x18000d6cb  movups  [rbp+840h+var_86C], xmm0
0x18000d6cf  movups  [rbp+840h+var_85C], xmm0
0x18000d6d3  mov     [rbp+840h+var_84C], eax
0x18000d6d6  movups  [rbp+840h+var_8A0], xmm0
0x18000d6da  xorps   xmm1, xmm1
0x18000d6dd  movdqu  [rsp+940h+var_8D0], xmm1
0x18000d6e3  mov     [rsp+940h+var_8D8], r13
0x18000d6e8  movdqu  [rbp+840h+var_8C0], xmm0
0x18000d6ed  mov     [rbp+840h+var_8B0], r13
0x18000d6f1  or      r14d, 0FFFFFFFFh
0x18000d6f5  mov     [rbp+840h+var_8A8], r14d
0x18000d6f9  mov     [rbp+840h+var_8A4], r13d
0x18000d6fd  mov     al, cs:byte_1800AA941
0x18000d703  test    al, 8
0x18000d705  jz      short loc_18000D73A
0x18000d707  mov     rax, [rdi+70h]
0x18000d70b  mov     [rsp+940h+var_920], rax; void *
0x18000d710  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18000d717  lea     r8, [rsp+940h+var_8E0]; unsigned int *
0x18000d71c  lea     rdx, aVpnikeconnecti_2; "VPNIKEConnection::CreateTunnel"
0x18000d723  lea     rcx, [rsp+940h+var_8D8]; this
0x18000d728  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18000d72d  mov     rbx, cs:WPP_GLOBAL_Control
0x18000d734  mov     al, cs:byte_1800AA941
0x18000d73a  mov     edx, [rdi+98h]
0x18000d740  bt      edx, 14h
0x18000d744  jnb     loc_18000D825
0x18000d74a  mov     [rsp+940h+var_8E0], 269h
0x18000d752  test    al, 4
0x18000d754  jz      loc_18000D7DD
0x18000d75a  mov     word ptr [rbp+840h+var_870], r13w
0x18000d75f  mov     rax, [rdi+70h]
0x18000d763  test    rax, rax
0x18000d766  jz      short loc_18000D772
0x18000d768  cmp     [rax+10h], r13
0x18000d76c  jz      short loc_18000D772
0x18000d76e  mov     r14d, [rax+10h]
0x18000d772  mov     edx, r14d
0x18000d775  lea     rcx, [rbp+840h+var_870]
0x18000d779  call    ConvertPortNoToString
0x18000d77e  test    cs:byte_1800AA941, 4
0x18000d785  jz      short loc_18000D7D6
0x18000d787  mov     rdx, [rdi+70h]
0x18000d78b  mov     rax, rdx
0x18000d78e  lea     rcx, [rdx+0A7Eh]
0x18000d795  neg     rax
0x18000d798  sbb     r8, r8
0x18000d79b  and     r8, rcx
0x18000d79e  test    rdx, rdx
0x18000d7a1  lea     r9, [rdx+848h]
0x18000d7a8  jnz     short loc_18000D7AE
0x18000d7aa  lea     r9, [rbp+840h+var_8A0]
0x18000d7ae  lea     rax, [rbp+840h+var_870]
0x18000d7b2  mov     [rsp+940h+var_918], rax
0x18000d7b7  mov     [rsp+940h+var_920], r8
0x18000d7bc  lea     r8, aDisconnectTrig; "Disconnect triggered on this connection"...
0x18000d7c3  lea     rdx, RasVpnIkeParamTraceError
0x18000d7ca  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d7d1  call    McTemplateU0zjzz_EventWriteTransfer
0x18000d7d6  mov     rbx, cs:WPP_GLOBAL_Control
0x18000d7dd  lea     rdi, WPP_GLOBAL_Control
0x18000d7e4  cmp     rbx, rdi
0x18000d7e7  jz      loc_18000DFE1
0x18000d7ed  test    byte ptr [rbx+1Ch], 1
0x18000d7f1  jz      loc_18000DFB6
0x18000d7f7  mov     r15d, 2
0x18000d7fd  cmp     [rbx+19h], r15b
0x18000d801  jb      loc_18000DFB6
0x18000d807  lea     edx, [r15+38h]
0x18000d80b  mov     r9d, [rsp+940h+var_8E0]
0x18000d810  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18000d817  mov     rcx, [rbx+10h]
0x18000d81b  call    WPP_SF_d
0x18000d820  jmp     loc_18000DFAF
0x18000d825  mov     r15d, 2
0x18000d82b  test    dl, 10h
0x18000d82e  jnz     loc_18000D8FE
0x18000d834  mov     rcx, [rdi+70h]
0x18000d838  cmp     [rcx+5C0h], r15d
0x18000d83f  jz      loc_18000D8FE
0x18000d845  mov     [rsp+940h+var_8E0], 364Ch
0x18000d84d  test    al, 4
0x18000d84f  jz      short loc_18000D8D0
0x18000d851  mov     word ptr [rbp+840h+var_870], r13w
0x18000d856  test    rcx, rcx
0x18000d859  jz      short loc_18000D865
0x18000d85b  cmp     [rcx+10h], r13
0x18000d85f  jz      short loc_18000D865
0x18000d861  mov     r14d, [rcx+10h]
0x18000d865  mov     edx, r14d
0x18000d868  lea     rcx, [rbp+840h+var_870]
0x18000d86c  call    ConvertPortNoToString
0x18000d871  test    cs:byte_1800AA941, 4
0x18000d878  jz      short loc_18000D8C9
0x18000d87a  mov     rdx, [rdi+70h]
0x18000d87e  mov     rax, rdx
0x18000d881  lea     rcx, [rdx+0A7Eh]
0x18000d888  neg     rax
0x18000d88b  sbb     r8, r8
0x18000d88e  and     r8, rcx
0x18000d891  test    rdx, rdx
0x18000d894  lea     r9, [rdx+848h]
0x18000d89b  jnz     short loc_18000D8A1
0x18000d89d  lea     r9, [rbp+840h+var_8A0]
0x18000d8a1  lea     rax, [rbp+840h+var_870]
0x18000d8a5  mov     [rsp+940h+var_918], rax
0x18000d8aa  mov     [rsp+940h+var_920], r8
0x18000d8af  lea     r8, aCreateTunnelCa; "Create tunnel called without Cfg proces"...
0x18000d8b6  lea     rdx, RasVpnIkeParamTraceError
0x18000d8bd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d8c4  call    McTemplateU0zjzz_EventWriteTransfer
0x18000d8c9  mov     rbx, cs:WPP_GLOBAL_Control
0x18000d8d0  lea     rdi, WPP_GLOBAL_Control
0x18000d8d7  cmp     rbx, rdi
0x18000d8da  jz      loc_18000DFE1
0x18000d8e0  test    byte ptr [rbx+1Ch], 1
0x18000d8e4  jz      loc_18000DFB6
0x18000d8ea  cmp     [rbx+19h], r15b
0x18000d8ee  jb      loc_18000DFB6
0x18000d8f4  mov     edx, 3Bh ; ';'
0x18000d8f9  jmp     loc_18000D80B
0x18000d8fe  test    dl, 20h
0x18000d901  jnz     loc_18000D9C8
0x18000d907  mov     [rsp+940h+var_8E0], 10DDh
0x18000d90f  test    al, 4
0x18000d911  jz      loc_18000D99A
0x18000d917  mov     word ptr [rbp+840h+var_870], r13w
0x18000d91c  mov     rax, [rdi+70h]
0x18000d920  test    rax, rax
0x18000d923  jz      short loc_18000D92F
0x18000d925  cmp     [rax+10h], r13
0x18000d929  jz      short loc_18000D92F
0x18000d92b  mov     r14d, [rax+10h]
0x18000d92f  mov     edx, r14d
0x18000d932  lea     rcx, [rbp+840h+var_870]
0x18000d936  call    ConvertPortNoToString
0x18000d93b  test    cs:byte_1800AA941, 4
0x18000d942  jz      short loc_18000D993
0x18000d944  mov     rdx, [rdi+70h]
0x18000d948  mov     rax, rdx
0x18000d94b  lea     rcx, [rdx+0A7Eh]
0x18000d952  neg     rax
0x18000d955  sbb     r8, r8
0x18000d958  and     r8, rcx
0x18000d95b  test    rdx, rdx
0x18000d95e  lea     r9, [rdx+848h]
0x18000d965  jnz     short loc_18000D96B
0x18000d967  lea     r9, [rbp+840h+var_8A0]
0x18000d96b  lea     rax, [rbp+840h+var_870]
0x18000d96f  mov     [rsp+940h+var_918], rax
0x18000d974  mov     [rsp+940h+var_920], r8
0x18000d979  lea     r8, aCreatetunnelCa; "CreateTunnel called in invalid state. H"...
0x18000d980  lea     rdx, RasVpnIkeParamTraceError
0x18000d987  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d98e  call    McTemplateU0zjzz_EventWriteTransfer
0x18000d993  mov     rbx, cs:WPP_GLOBAL_Control
0x18000d99a  lea     rdi, WPP_GLOBAL_Control
0x18000d9a1  cmp     rbx, rdi
0x18000d9a4  jz      loc_18000DFE1
0x18000d9aa  test    byte ptr [rbx+1Ch], 1
0x18000d9ae  jz      loc_18000DFB6
0x18000d9b4  cmp     [rbx+19h], r15b
0x18000d9b8  jb      loc_18000DFB6
0x18000d9be  mov     edx, 3Ch ; '<'
0x18000d9c3  jmp     loc_18000D80B
0x18000d9c8  mov     rax, [rdi+70h]
0x18000d9cc  cmp     dword ptr [rax+109Ch], 1
0x18000d9d3  jnz     short loc_18000D9DD
0x18000d9d5  mov     rcx, rdi; this
0x18000d9d8  call    ?RegisterForLowPowerModeNetEvent@VPNIKEConnection@@QEAAXXZ; VPNIKEConnection::RegisterForLowPowerModeNetEvent(void)
0x18000d9dd  mov     edx, 4; unsigned int
0x18000d9e2  mov     rcx, rdi; this
0x18000d9e5  call    ?UpdateConnectionState@VPNIKEConnection@@IEAAXK@Z; VPNIKEConnection::UpdateConnectionState(ulong)
0x18000d9ea  mov     rdx, rsi; struct _IKETUNNEL_PARAMETERS_ *
0x18000d9ed  mov     rcx, rdi; this
0x18000d9f0  call    ?UpdateVPNIKETunnelParams@VPNIKEConnection@@IEAAXAEAU_IKETUNNEL_PARAMETERS_@@@Z; VPNIKEConnection::UpdateVPNIKETunnelParams(_IKETUNNEL_PARAMETERS_ &)
0x18000d9f5  cmp     [rdi+108h], r13b
0x18000d9fc  jz      loc_18000DB7A
0x18000da02  cmp     [rdi+109h], r13b
0x18000da09  jz      loc_18000DB7A
0x18000da0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da16  lea     rbx, WPP_GLOBAL_Control
0x18000da1d  cmp     rcx, rbx
0x18000da20  jz      short loc_18000DA43
0x18000da22  test    byte ptr [rcx+1Ch], 1
0x18000da26  jz      short loc_18000DA43
0x18000da28  cmp     byte ptr [rcx+19h], 5
0x18000da2c  jb      short loc_18000DA43
0x18000da2e  mov     edx, 3Dh ; '='
0x18000da33  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18000da3a  mov     rcx, [rcx+10h]
0x18000da3e  call    WPP_SF_
0x18000da43  xorps   xmm0, xmm0
0x18000da46  movups  [rbp+840h+var_890+2], xmm0
0x18000da4a  movups  [rbp+840h+var_890+0Ch], xmm0
0x18000da4e  cmp     [rdi+10h], r13b
0x18000da52  jz      short loc_18000DA61
0x18000da54  mov     word ptr [rbp+840h+var_890], r15w
0x18000da59  mov     eax, [rdi+30h]
0x18000da5c  mov     dword ptr [rbp+840h+var_890+4], eax
0x18000da5f  jmp     short loc_18000DA73
0x18000da61  mov     eax, 17h
0x18000da66  mov     word ptr [rbp+840h+var_890], ax
0x18000da6a  movups  xmm0, xmmword ptr [rdi+34h]
0x18000da6e  movdqu  [rbp+840h+var_890+8], xmm0
0x18000da73  mov     rcx, [rdi+0E8h]
0x18000da7a  mov     rax, [rcx]
0x18000da7d  lea     rdx, [rdi+8]
0x18000da81  mov     r9d, [rdi+6Ch]
0x18000da85  lea     r8, [rbp+840h+var_890]
0x18000da89  mov     rax, [rax]
0x18000da8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da91  mov     [rsp+940h+var_8E0], eax
0x18000da95  test    eax, eax
0x18000da97  jz      loc_18000DC00
0x18000da9d  test    cs:byte_1800AA941, 4
0x18000daa4  jz      loc_18000DB3E
0x18000daaa  mov     word ptr [rbp+840h+var_840], r13w
0x18000daaf  mov     word ptr [rbp+840h+var_870], r13w
0x18000dab4  mov     rax, [rdi+70h]
0x18000dab8  test    rax, rax
0x18000dabb  jz      short loc_18000DAC8
0x18000dabd  cmp     [rax+10h], r13
0x18000dac1  jz      short loc_18000DAC8
0x18000dac3  mov     edx, [rax+10h]
0x18000dac6  jmp     short loc_18000DACB
0x18000dac8  mov     edx, r14d
0x18000dacb  lea     rcx, [rbp+840h+var_870]
0x18000dacf  call    ConvertPortNoToString
0x18000dad4  mov     r8d, [rsp+940h+var_8E0]
0x18000dad9  lea     rdx, aAddormodifyipa; "AddOrModifyIPAddressChangeForConnection"...
0x18000dae0  lea     rcx, [rbp+840h+var_840]
0x18000dae4  call    FormatRRASErrorString
0x18000dae9  test    cs:byte_1800AA941, 4
0x18000daf0  jz      short loc_18000DB3E
0x18000daf2  mov     rdx, [rdi+70h]
0x18000daf6  mov     rax, rdx
0x18000daf9  lea     rcx, [rdx+0A7Eh]
0x18000db00  neg     rax
0x18000db03  sbb     r8, r8
0x18000db06  and     r8, rcx
0x18000db09  test    rdx, rdx
0x18000db0c  lea     r9, [rdx+848h]
0x18000db13  jnz     short loc_18000DB19
0x18000db15  lea     r9, [rbp+840h+var_8A0]
0x18000db19  lea     rax, [rbp+840h+var_870]
0x18000db1d  mov     [rsp+940h+var_918], rax
0x18000db22  mov     [rsp+940h+var_920], r8
0x18000db27  lea     r8, [rbp+840h+var_840]
0x18000db2b  lea     rdx, RasVpnIkeParamTraceError
0x18000db32  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000db39  call    McTemplateU0zjzz_EventWriteTransfer
0x18000db3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db45  cmp     rcx, rbx
0x18000db48  jz      short loc_18000DB70
0x18000db4a  test    byte ptr [rcx+1Ch], 1
0x18000db4e  jz      short loc_18000DB70
  ... truncated ...
```
