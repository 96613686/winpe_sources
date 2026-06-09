# VPNIKEConnection::UpdateRoutes(void)

- ea: `0x1800135b0`
- end: `0x180013f8c`
- name: `?UpdateRoutes@VPNIKEConnection@@IEAAKXZ`
- size: `2524`
- prototype: `unsigned int __fastcall(VPNIKEConnection *__hidden this)`
- caller_count: `2`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800170a0`
- `0x1800221b0`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x1800135b0`
- `0x180014bec`
- `0x18004b20c`
- `0x18004b840`
- `0x18004fca8`
- `0x18004fdf4`
- `0x18005dce0`
- `0x18005de2c`
- `0x180075a3c`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `rtutils!RouterLogEventA` at `0x180013b4f`
- `rtutils!RouterLogEventA` at `0x180013c4a`
- `rtutils!RouterLogEventA` at `0x180013b4f`
- `rtutils!RouterLogEventA` at `0x180013c4a`

## string_xrefs

- `0x180013710`: `VPNIKEConnection::UpdateRoutes`
- `0x1800138d7`: `VPNIKEProtocolEngine::PEHelperFunctions.lpfnRouterTypeLookup failed with error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VPNIKEConnection::UpdateRoutes(VPNIKEConnection *this)
{
  PVOID *v2; // rdi
  _DWORD *v3; // rsi
  int v4; // r15d
  int v5; // r12d
  unsigned int v6; // r8d
  __int64 v7; // r9
  unsigned int v8; // r14d
  unsigned int RemoteUserName; // eax
  unsigned int v10; // r8d
  unsigned int PortName; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  PVOID *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rax
  __int64 v20; // rdx
  __int128 *v21; // r9
  PVOID *v22; // rcx
  __int64 v23; // rdx
  char v24; // al
  int v25; // esi
  int v26; // edi
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int128 *v36; // r9
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int128 *v40; // r9
  __int64 v41; // rax
  __int64 v42; // rdx
  __int128 *v43; // r9
  __int64 v44; // rax
  __int64 v45; // rdx
  __int128 *v46; // r9
  __int64 v47; // rax
  __int64 v48; // rdx
  __int128 *v49; // r9
  unsigned int v50; // ebx
  int plpszSubStringArray; // [rsp+20h] [rbp-E0h]
  unsigned int v53; // [rsp+30h] [rbp-D0h] BYREF
  int v54; // [rsp+34h] [rbp-CCh] BYREF
  LPSTR v55; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v56; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v57; // [rsp+48h] [rbp-B8h]
  __int128 v58; // [rsp+58h] [rbp-A8h]
  __int64 v59; // [rsp+68h] [rbp-98h]
  int v60; // [rsp+70h] [rbp-90h]
  int v61; // [rsp+74h] [rbp-8Ch]
  __int128 v62; // [rsp+78h] [rbp-88h] BYREF
  __int128 v63; // [rsp+88h] [rbp-78h] BYREF
  int v64; // [rsp+98h] [rbp-68h] BYREF
  __int128 v65; // [rsp+9Ch] [rbp-64h]
  __int128 v66; // [rsp+ACh] [rbp-54h]
  int v67; // [rsp+BCh] [rbp-44h]
  unsigned __int16 v68[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v69; // [rsp+D0h] [rbp-30h]
  __int16 v70; // [rsp+E0h] [rbp-20h]
  _OWORD v71[3]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v72[30]; // [rsp+120h] [rbp+20h]
  __int16 v73; // [rsp+13Eh] [rbp+3Eh]
  unsigned __int16 v74[280]; // [rsp+140h] [rbp+40h] BYREF
  int v75; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v76[2044]; // [rsp+374h] [rbp+274h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v53 = 0;
  memset_0(v74, 0, 0x222u);
  *(_OWORD *)v68 = 0;
  v69 = 0;
  v70 = 0;
  v3 = (_DWORD *)*((_QWORD *)this + 14);
  v4 = v3[368];
  v5 = v3[10];
  v55 = 0;
  v71[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v71[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v71[2] = *(_OWORD *)L"000-0000-000000000000}";
  *(_OWORD *)v72 = *(_OWORD *)L"-000000000000}";
  *(_OWORD *)&v72[14] = *(_OWORD *)L"000000}";
  v73 = 0;
  v63 = 0;
  v75 = 0;
  memset_0(v76, 0, sizeof(v76));
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v62 = 0;
  v57 = 0;
  v56 = 0;
  v58 = 0;
  v59 = 0;
  v8 = -1;
  v60 = -1;
  v61 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v56,
      L"VPNIKEConnection::UpdateRoutes",
      &v53,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      v3);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
  {
    LOBYTE(v7) = v4 == 2;
    LOBYTE(plpszSubStringArray) = v5 == 2;
    WPP_SF_cc(v2[2], 43, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, v7, plpszSubStringArray);
  }
  RemoteUserName = BaseConnection::GetRemoteUserName(this, v74, v6);
  if ( RemoteUserName
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, RemoteUserName);
  }
  PortName = BaseConnection::GetPortName(this, v68, v10);
  if ( !PortName )
    goto LABEL_21;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, PortName);
LABEL_21:
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 == 2 )
  {
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
      WPP_SF_(v15[2], 49, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
    v30 = *((_QWORD *)this + 14);
    if ( !*(_BYTE *)(v30 + 4428) || (v25 = 1, *(_QWORD *)(v30 + 1480) == -1) )
      v25 = 0;
    if ( !*(_BYTE *)(v30 + 4429) || (v26 = 1, *(_QWORD *)(v30 + 1488) == -1) )
      v26 = 0;
    v63 = *(_OWORD *)(v30 + 2120);
    MprConvertGuidToString(&v63, v12, v71);
    v55 = (LPSTR)v71;
    if ( !v25 && IPv4Helper::DoNegotiate(*((IPv4Helper **)this + 4), v31, v32, v18) )
    {
      if ( (byte_1800AA941 & 1) != 0 )
      {
        LOWORD(v64) = 0;
        v33 = *((_QWORD *)this + 14);
        if ( v33 && *(_QWORD *)(v33 + 16) )
          v34 = *(unsigned int *)(v33 + 16);
        else
          v34 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v64, v34);
        if ( (byte_1800AA941 & 1) != 0 )
        {
          v35 = *((_QWORD *)this + 14);
          LODWORD(v36) = v35 + 2120;
          if ( !v35 )
            v36 = &v62;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceAdminError,
            (unsigned int)L"IPv4 routes are not added as IPv4 transport is not available on the interface.",
            (_DWORD)v36,
            (v35 + 2686) & -(__int64)(v35 != 0),
            (__int64)&v64);
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
      }
      RouterLogEventA(*((HANDLE *)VpnIkeProtocolEngine + 2), 2u, 0x4F40u, 1u, &v55, 0);
    }
    if ( !v26 && IPv6Helper::DoNegotiate(*((IPv6Helper **)this + 5), v31, v32, v18) )
    {
      if ( (byte_1800AA941 & 1) != 0 )
      {
        LOWORD(v64) = 0;
        v37 = *((_QWORD *)this + 14);
        if ( v37 && *(_QWORD *)(v37 + 16) )
          v38 = *(unsigned int *)(v37 + 16);
        else
          v38 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v64, v38);
        if ( (byte_1800AA941 & 1) != 0 )
        {
          v39 = *((_QWORD *)this + 14);
          LODWORD(v40) = v39 + 2120;
          if ( !v39 )
            v40 = &v62;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceAdminError,
            (unsigned int)L"IPv6 routes are not added as IPv6 transport is not available on the interface.",
            (_DWORD)v40,
            (v39 + 2686) & -(__int64)(v39 != 0),
            (__int64)&v64);
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
      }
      RouterLogEventA(*((HANDLE *)VpnIkeProtocolEngine + 2), 2u, 0x4F41u, 1u, &v55, 0);
    }
  }
  else
  {
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
    {
      WPP_SF_(v15[2], 46, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 == 2 )
    {
      if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
        WPP_SF_(v15[2], 47, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
      v54 = 0;
      v63 = *(_OWORD *)(*((_QWORD *)this + 14) + 2120LL);
      v53 = VPNIKEProtocolEngine::PEHelperFunctions(&v63, &v54);
      if ( v53 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v75) = 0;
          LOWORD(v64) = 0;
          v19 = *((_QWORD *)this + 14);
          if ( v19 && *(_QWORD *)(v19 + 16) )
            v8 = *(_DWORD *)(v19 + 16);
          ConvertPortNoToString(&v64, v8);
          FormatRRASErrorString(
            &v75,
            L"VPNIKEProtocolEngine::PEHelperFunctions.lpfnRouterTypeLookup failed with error %d",
            v53);
          if ( (byte_1800AA941 & 4) != 0 )
          {
            v20 = *((_QWORD *)this + 14);
            LODWORD(v21) = v20 + 2120;
            if ( !v20 )
              v21 = &v62;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v75,
              (_DWORD)v21,
              (v20 + 2686) & -(__int64)(v20 != 0),
              (__int64)&v64);
          }
        }
        v22 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v23 = 48;
LABEL_143:
            WPP_SF_d(v22[2], v23, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, v53);
            v22 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_144;
          }
          goto LABEL_144;
        }
        goto LABEL_148;
      }
      v24 = v54;
      if ( (v54 & 1) != 0 )
      {
        v25 = IPv4Helper::DoNegotiate(*((IPv4Helper **)this + 4), v16, v17, v18);
        v24 = v54;
      }
      else
      {
        v25 = 0;
      }
      if ( (v24 & 8) != 0 )
        v26 = IPv6Helper::DoNegotiate(*((IPv6Helper **)this + 5), v16, v17, v18);
      else
        v26 = 0;
    }
    else
    {
      v25 = IPv4Helper::DoNegotiate(*((IPv4Helper **)this + 4), v12, v13, v14);
      v26 = IPv6Helper::DoNegotiate(*((IPv6Helper **)this + 5), v27, v28, v29);
    }
  }
  v22 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    LOBYTE(v18) = v25 != 0;
    LOBYTE(plpszSubStringArray) = v26 != 0;
    WPP_SF_cc(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids,
      v18,
      plpszSubStringArray);
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v25 )
  {
LABEL_113:
    if ( v26 )
    {
      v53 = IPv6Helper::PostConnectActions(*((IPv6Helper **)this + 5), v74, v68);
      if ( v53 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v64) = 0;
          v44 = *((_QWORD *)this + 14);
          if ( v44 && *(_QWORD *)(v44 + 16) )
            v8 = *(_DWORD *)(v44 + 16);
          ConvertPortNoToString(&v64, v8);
          if ( (byte_1800AA941 & 4) != 0 )
          {
            v45 = *((_QWORD *)this + 14);
            LODWORD(v46) = v45 + 2120;
            if ( !v45 )
              v46 = &v62;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)L"Localipv6->PostConnectActions failed",
              (_DWORD)v46,
              (v45 + 2686) & -(__int64)(v45 != 0),
              (__int64)&v64);
          }
        }
        v22 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v23 = 54;
            goto LABEL_143;
          }
          goto LABEL_144;
        }
        goto LABEL_148;
      }
      v22 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v25 || v26 )
      goto LABEL_144;
    v53 = 720;
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v64) = 0;
      v47 = *((_QWORD *)this + 14);
      if ( v47 && *(_QWORD *)(v47 + 16) )
        v8 = *(_DWORD *)(v47 + 16);
      ConvertPortNoToString(&v64, v8);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v48 = *((_QWORD *)this + 14);
        LODWORD(v49) = v48 + 2120;
        if ( !v48 )
          v49 = &v62;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Neither IPv4 nor IPv6 routes are plumbed - tearing down the connection.",
          (_DWORD)v49,
          (v48 + 2686) & -(__int64)(v48 != 0),
          (__int64)&v64);
      }
      v22 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v22 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v22 + 28) & 1) != 0 && *((_BYTE *)v22 + 25) >= 2u )
      {
        v23 = 55;
        goto LABEL_143;
      }
      goto LABEL_144;
    }
    goto LABEL_148;
  }
  v53 = IPv4Helper::PostConnectActions(*((IPv4Helper **)this + 4), v74, v68);
  if ( !v53 )
  {
    v22 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_113;
  }
  if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v64) = 0;
    v41 = *((_QWORD *)this + 14);
    if ( v41 && *(_QWORD *)(v41 + 16) )
      v8 = *(_DWORD *)(v41 + 16);
    ConvertPortNoToString(&v64, v8);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v42 = *((_QWORD *)this + 14);
      LODWORD(v43) = v42 + 2120;
      if ( !v42 )
        v43 = &v62;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceError,
        (unsigned int)L"Localipv4->PostConnectActions failed",
        (_DWORD)v43,
        (v42 + 2686) & -(__int64)(v42 != 0),
        (__int64)&v64);
    }
  }
  v22 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = 53;
      goto LABEL_143;
    }
LABEL_144:
    if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 1) != 0 && *((_BYTE *)v22 + 25) >= 6u )
      WPP_SF_d(v22[2], 56, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, v53);
  }
LABEL_148:
  v50 = v53;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v56);
  return v50;
}

```

## disassembly

```asm
0x1800135b0  push    rbp
0x1800135b2  push    rbx
0x1800135b3  push    rsi
0x1800135b4  push    rdi
0x1800135b5  push    r12
0x1800135b7  push    r13
0x1800135b9  push    r14
0x1800135bb  push    r15
0x1800135bd  lea     rbp, [rsp-0A88h]
0x1800135c5  sub     rsp, 0B88h
0x1800135cc  mov     rax, cs:__security_cookie
0x1800135d3  xor     rax, rsp
0x1800135d6  mov     [rbp+0AC0h+var_50], rax
0x1800135dd  mov     rbx, rcx
0x1800135e0  lea     rax, WPP_GLOBAL_Control
0x1800135e7  mov     rdi, cs:WPP_GLOBAL_Control
0x1800135ee  cmp     rdi, rax
0x1800135f1  jz      short loc_18001361B
0x1800135f3  test    byte ptr [rdi+1Ch], 1
0x1800135f7  jz      short loc_18001361B
0x1800135f9  cmp     byte ptr [rdi+19h], 6
0x1800135fd  jb      short loc_18001361B
0x1800135ff  mov     edx, 2Ah ; '*'
0x180013604  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18001360b  mov     rcx, [rdi+10h]
0x18001360f  call    WPP_SF_
0x180013614  mov     rdi, cs:WPP_GLOBAL_Control
0x18001361b  xor     r13d, r13d
0x18001361e  mov     [rsp+0BC0h+var_B90], r13d
0x180013623  xor     edx, edx; Val
0x180013625  mov     r8d, 222h; Size
0x18001362b  lea     rcx, [rbp+0AC0h+var_A80]; void *
0x18001362f  call    memset_0
0x180013634  xorps   xmm0, xmm0
0x180013637  xor     eax, eax
0x180013639  movups  xmmword ptr [rbp+0AC0h+var_B00], xmm0
0x18001363d  movups  [rbp+0AC0h+var_AF0], xmm0
0x180013641  mov     [rbp+0AC0h+var_AE0], ax
0x180013645  mov     rsi, [rbx+70h]
0x180013649  mov     r15d, [rsi+5C0h]
0x180013650  mov     r12d, [rsi+28h]
0x180013654  mov     [rsp+0BC0h+var_B88], r13
0x180013659  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180013660  movaps  [rbp+0AC0h+var_AD0], xmm0
0x180013664  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x18001366b  movaps  [rbp+0AC0h+var_AC0], xmm1
0x18001366f  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x180013676  movaps  [rbp+0AC0h+var_AB0], xmm0
0x18001367a  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x180013681  movaps  xmmword ptr [rbp+0AC0h+var_AA0], xmm1
0x180013685  movups  xmm0, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x18001368c  movups  xmmword ptr [rbp+0AC0h+var_AA0+0Eh], xmm0
0x180013690  mov     [rbp+0AC0h+var_A82], ax
0x180013694  xorps   xmm0, xmm0
0x180013697  movups  [rbp+0AC0h+var_B38], xmm0
0x18001369b  mov     [rbp+0AC0h+var_850], r13d
0x1800136a2  xor     edx, edx; Val
0x1800136a4  mov     r8d, 7FCh; Size
0x1800136aa  lea     rcx, [rbp+0AC0h+var_84C]; void *
0x1800136b1  call    memset_0
0x1800136b6  mov     [rbp+0AC0h+var_B28], r13d
0x1800136ba  xorps   xmm0, xmm0
0x1800136bd  xor     eax, eax
0x1800136bf  movups  [rbp+0AC0h+var_B24], xmm0
0x1800136c3  movups  [rbp+0AC0h+var_B14], xmm0
0x1800136c7  mov     [rbp+0AC0h+var_B04], eax
0x1800136ca  movups  [rsp+0BC0h+var_B48], xmm0
0x1800136cf  xorps   xmm1, xmm1
0x1800136d2  movdqu  [rsp+0BC0h+var_B78], xmm1
0x1800136d8  mov     [rsp+0BC0h+var_B80], r13
0x1800136dd  movdqu  [rsp+0BC0h+var_B68], xmm0
0x1800136e3  mov     [rsp+0BC0h+var_B58], r13
0x1800136e8  or      r14d, 0FFFFFFFFh
0x1800136ec  mov     [rsp+0BC0h+var_B50], r14d
0x1800136f1  mov     [rsp+0BC0h+var_B4C], r13d
0x1800136f6  test    cs:byte_1800AA941, 8
0x1800136fd  jz      short loc_180013728
0x1800136ff  mov     [rsp+0BC0h+plpszSubStringArray], rsi; void *
0x180013704  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18001370b  lea     r8, [rsp+0BC0h+var_B90]; unsigned int *
0x180013710  lea     rdx, aVpnikeconnecti_22; "VPNIKEConnection::UpdateRoutes"
0x180013717  lea     rcx, [rsp+0BC0h+var_B80]; this
0x18001371c  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x180013721  mov     rdi, cs:WPP_GLOBAL_Control
0x180013728  lea     rsi, WPP_GLOBAL_Control
0x18001372f  cmp     rdi, rsi
0x180013732  jz      short loc_180013768
0x180013734  test    byte ptr [rdi+1Ch], 1
0x180013738  jz      short loc_180013768
0x18001373a  cmp     byte ptr [rdi+19h], 5
0x18001373e  jb      short loc_180013768
0x180013740  cmp     r12d, 2
0x180013744  setz    al
0x180013747  cmp     r15d, 2
0x18001374b  setz    r9b
0x18001374f  mov     edx, 2Bh ; '+'
0x180013754  mov     byte ptr [rsp+0BC0h+plpszSubStringArray], al
0x180013758  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18001375f  mov     rcx, [rdi+10h]
0x180013763  call    WPP_SF_cc
0x180013768  lea     rdx, [rbp+0AC0h+var_A80]; unsigned __int16 *
0x18001376c  mov     rcx, rbx; this
0x18001376f  call    ?GetRemoteUserName@BaseConnection@@QEAAKPEAGK@Z; BaseConnection::GetRemoteUserName(ushort *,ulong)
0x180013774  test    eax, eax
0x180013776  jz      short loc_1800137A8
0x180013778  mov     rcx, cs:WPP_GLOBAL_Control
0x18001377f  cmp     rcx, rsi
0x180013782  jz      short loc_1800137A8
0x180013784  test    byte ptr [rcx+1Ch], 1
0x180013788  jz      short loc_1800137A8
0x18001378a  cmp     byte ptr [rcx+19h], 3
0x18001378e  jb      short loc_1800137A8
0x180013790  mov     edx, 2Ch ; ','
0x180013795  mov     r9d, eax
0x180013798  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18001379f  mov     rcx, [rcx+10h]
0x1800137a3  call    WPP_SF_d
0x1800137a8  lea     rdx, [rbp+0AC0h+var_B00]; unsigned __int16 *
0x1800137ac  mov     rcx, rbx; this
0x1800137af  call    ?GetPortName@BaseConnection@@QEAAKPEAGK@Z; BaseConnection::GetPortName(ushort *,ulong)
0x1800137b4  test    eax, eax
0x1800137b6  jz      short loc_1800137E8
0x1800137b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800137bf  cmp     rcx, rsi
0x1800137c2  jz      short loc_1800137EF
0x1800137c4  test    byte ptr [rcx+1Ch], 1
0x1800137c8  jz      short loc_1800137EF
0x1800137ca  cmp     byte ptr [rcx+19h], 3
0x1800137ce  jb      short loc_1800137EF
0x1800137d0  mov     edx, 2Dh ; '-'
0x1800137d5  mov     r9d, eax
0x1800137d8  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x1800137df  mov     rcx, [rcx+10h]
0x1800137e3  call    WPP_SF_d
0x1800137e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800137ef  cmp     r15d, 2
0x1800137f3  jz      loc_1800139CF
0x1800137f9  lea     r15, WPP_GLOBAL_Control
0x180013800  cmp     rcx, r15
0x180013803  jz      short loc_18001382D
0x180013805  test    byte ptr [rcx+1Ch], 1
0x180013809  jz      short loc_18001382D
0x18001380b  cmp     byte ptr [rcx+19h], 5
0x18001380f  jb      short loc_18001382D
0x180013811  mov     edx, 2Eh ; '.'
0x180013816  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18001381d  mov     rcx, [rcx+10h]
0x180013821  call    WPP_SF_
0x180013826  mov     rcx, cs:WPP_GLOBAL_Control
0x18001382d  cmp     r12d, 2
0x180013831  jnz     loc_1800139AC
0x180013837  mov     r12d, 1
0x18001383d  cmp     rcx, r15
0x180013840  jz      short loc_180013863
0x180013842  test    [rcx+1Ch], r12b
0x180013846  jz      short loc_180013863
0x180013848  cmp     byte ptr [rcx+19h], 5
0x18001384c  jb      short loc_180013863
0x18001384e  lea     edx, [r12+2Eh]
0x180013853  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18001385a  mov     rcx, [rcx+10h]
0x18001385e  call    WPP_SF_
0x180013863  mov     [rsp+0BC0h+var_B8C], r13d
0x180013868  mov     rax, [rbx+70h]
0x18001386c  movups  xmm0, xmmword ptr [rax+848h]
0x180013873  movdqu  [rbp+0AC0h+var_B38], xmm0
0x180013878  lea     rdx, [rsp+0BC0h+var_B8C]
0x18001387d  lea     rcx, [rbp+0AC0h+var_B38]
0x180013881  mov     rax, qword ptr cs:?PEHelperFunctions@VPNIKEProtocolEngine@@2U_PROTOCOL_ENGINE_HELPER_FUNCTIONS@@A; _PROTOCOL_ENGINE_HELPER_FUNCTIONS VPNIKEProtocolEngine::PEHelperFunctions
0x180013888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001388d  mov     [rsp+0BC0h+var_B90], eax
0x180013891  test    eax, eax
0x180013893  jz      loc_180013971
0x180013899  test    cs:byte_1800AA941, 4
0x1800138a0  jz      loc_180013943
0x1800138a6  mov     word ptr [rbp+0AC0h+var_850], r13w
0x1800138ae  mov     word ptr [rbp+0AC0h+var_B28], r13w
0x1800138b3  mov     rax, [rbx+70h]
0x1800138b7  test    rax, rax
0x1800138ba  jz      short loc_1800138C6
0x1800138bc  cmp     [rax+10h], r13
0x1800138c0  jz      short loc_1800138C6
0x1800138c2  mov     r14d, [rax+10h]
0x1800138c6  mov     edx, r14d
0x1800138c9  lea     rcx, [rbp+0AC0h+var_B28]
0x1800138cd  call    ConvertPortNoToString
0x1800138d2  mov     r8d, [rsp+0BC0h+var_B90]
0x1800138d7  lea     rdx, aVpnikeprotocol_2; "VPNIKEProtocolEngine::PEHelperFunctions"...
0x1800138de  lea     rcx, [rbp+0AC0h+var_850]
0x1800138e5  call    FormatRRASErrorString
0x1800138ea  test    cs:byte_1800AA941, 4
0x1800138f1  jz      short loc_180013943
0x1800138f3  mov     rdx, [rbx+70h]
0x1800138f7  mov     rax, rdx
0x1800138fa  lea     rcx, [rdx+0A7Eh]
0x180013901  neg     rax
0x180013904  sbb     r8, r8
0x180013907  and     r8, rcx
0x18001390a  test    rdx, rdx
0x18001390d  lea     r9, [rdx+848h]
0x180013914  jnz     short loc_18001391B
0x180013916  lea     r9, [rsp+0BC0h+var_B48]
0x18001391b  lea     rax, [rbp+0AC0h+var_B28]
0x18001391f  mov     qword ptr [rsp+0BC0h+dwErrorCode], rax
0x180013924  mov     [rsp+0BC0h+plpszSubStringArray], r8
0x180013929  lea     r8, [rbp+0AC0h+var_850]
0x180013930  lea     rdx, RasVpnIkeParamTraceError
0x180013937  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001393e  call    McTemplateU0zjzz_EventWriteTransfer
0x180013943  mov     rcx, cs:WPP_GLOBAL_Control
0x18001394a  cmp     rcx, r15
0x18001394d  jz      loc_180013F59
0x180013953  test    [rcx+1Ch], r12b
0x180013957  jz      loc_180013F2E
0x18001395d  cmp     byte ptr [rcx+19h], 2
0x180013961  jb      loc_180013F2E
0x180013967  mov     edx, 30h ; '0'
0x18001396c  jmp     loc_180013F12
0x180013971  mov     eax, [rsp+0BC0h+var_B8C]
0x180013975  test    r12b, al
0x180013978  jnz     short loc_18001397F
0x18001397a  mov     esi, r13d
0x18001397d  jmp     short loc_18001398F
0x18001397f  mov     rcx, [rbx+20h]; this
0x180013983  call    ?DoNegotiate@IPv4Helper@@QEAAEXZ; IPv4Helper::DoNegotiate(void)
0x180013988  movzx   esi, al
0x18001398b  mov     eax, [rsp+0BC0h+var_B8C]
0x18001398f  test    al, 8
0x180013991  jnz     short loc_18001399B
0x180013993  mov     edi, r13d
0x180013996  jmp     loc_180013C50
0x18001399b  mov     rcx, [rbx+28h]; this
0x18001399f  call    ?DoNegotiate@IPv6Helper@@QEAAEXZ; IPv6Helper::DoNegotiate(void)
0x1800139a4  movzx   edi, al
0x1800139a7  jmp     loc_180013C50
0x1800139ac  mov     rcx, [rbx+20h]; this
0x1800139b0  call    ?DoNegotiate@IPv4Helper@@QEAAEXZ; IPv4Helper::DoNegotiate(void)
0x1800139b5  movzx   esi, al
0x1800139b8  mov     rcx, [rbx+28h]; this
0x1800139bc  call    ?DoNegotiate@IPv6Helper@@QEAAEXZ; IPv6Helper::DoNegotiate(void)
0x1800139c1  movzx   edi, al
0x1800139c4  mov     r12d, 1
0x1800139ca  jmp     loc_180013C50
0x1800139cf  lea     r15, WPP_GLOBAL_Control
0x1800139d6  mov     r12d, 1
0x1800139dc  cmp     rcx, r15
0x1800139df  jz      short loc_180013A02
0x1800139e1  test    [rcx+1Ch], r12b
0x1800139e5  jz      short loc_180013A02
0x1800139e7  cmp     byte ptr [rcx+19h], 5
0x1800139eb  jb      short loc_180013A02
0x1800139ed  lea     edx, [r12+30h]
0x1800139f2  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x1800139f9  mov     rcx, [rcx+10h]
0x1800139fd  call    WPP_SF_
0x180013a02  mov     rax, [rbx+70h]
0x180013a06  cmp     [rax+114Ch], r13b
0x180013a0d  jz      short loc_180013A1C
0x180013a0f  cmp     qword ptr [rax+5C8h], 0FFFFFFFFFFFFFFFFh
0x180013a17  mov     esi, r12d
0x180013a1a  jnz     short loc_180013A1F
0x180013a1c  mov     esi, r13d
0x180013a1f  cmp     [rax+114Dh], r13b
0x180013a26  jz      short loc_180013A35
0x180013a28  cmp     qword ptr [rax+5D0h], 0FFFFFFFFFFFFFFFFh
0x180013a30  mov     edi, r12d
0x180013a33  jnz     short loc_180013A38
0x180013a35  mov     edi, r13d
0x180013a38  movups  xmm0, xmmword ptr [rax+848h]
0x180013a3f  movdqu  [rbp+0AC0h+var_B38], xmm0
0x180013a44  lea     r8, [rbp+0AC0h+var_AD0]
0x180013a48  lea     rcx, [rbp+0AC0h+var_B38]
0x180013a4c  call    MprConvertGuidToString
0x180013a51  lea     rax, [rbp+0AC0h+var_AD0]
0x180013a55  mov     [rsp+0BC0h+var_B88], rax
0x180013a5a  test    esi, esi
0x180013a5c  jnz     loc_180013B55
0x180013a62  mov     rcx, [rbx+20h]; this
0x180013a66  call    ?DoNegotiate@IPv4Helper@@QEAAEXZ; IPv4Helper::DoNegotiate(void)
0x180013a6b  test    al, al
0x180013a6d  jz      loc_180013B55
0x180013a73  test    cs:byte_1800AA941, r12b
0x180013a7a  jz      short loc_180013AFA
0x180013a7c  mov     word ptr [rbp+0AC0h+var_B28], r13w
0x180013a81  mov     rax, [rbx+70h]
0x180013a85  test    rax, rax
0x180013a88  jz      short loc_180013A95
0x180013a8a  cmp     [rax+10h], r13
0x180013a8e  jz      short loc_180013A95
0x180013a90  mov     edx, [rax+10h]
0x180013a93  jmp     short loc_180013A98
0x180013a95  mov     edx, r14d
0x180013a98  lea     rcx, [rbp+0AC0h+var_B28]
0x180013a9c  call    ConvertPortNoToString
0x180013aa1  test    cs:byte_1800AA941, r12b
0x180013aa8  jz      short loc_180013AFA
0x180013aaa  mov     rdx, [rbx+70h]
0x180013aae  mov     rax, rdx
0x180013ab1  lea     rcx, [rdx+0A7Eh]
0x180013ab8  neg     rax
  ... truncated ...
```
