# ServerBFEHandler::PlumbPolicyForRemoteIpAddr(_ROUTER_IP_ADDRESS *,_ROUTER_IP_ADDRESS *,IKEEXT_POLICY2_ *,IPSEC_TUNNEL_POLICY2_ *,_GUID *,_GUID *,_GUID *,_GUID *)

- ea: `0x18003d434`
- end: `0x18003da8b`
- name: `?PlumbPolicyForRemoteIpAddr@ServerBFEHandler@@KAKPEAU_ROUTER_IP_ADDRESS@@0PEAUIKEEXT_POLICY2_@@PEAUIPSEC_TUNNEL_POLICY2_@@PEAU_GUID@@333@Z`
- size: `1623`
- prototype: `__int64 __fastcall(struct _ROUTER_IP_ADDRESS *, struct _ROUTER_IP_ADDRESS *, struct IKEEXT_POLICY2_ *, struct IPSEC_TUNNEL_POLICY2_ *, struct _GUID *, struct _GUID *, struct _GUID *, struct _GUID *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003a470`
- `0x18003bdb4`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x18002e6f4`
- `0x18003d434`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `fwpuclnt!FwpmIPsecTunnelAdd2` at `0x18003d768`
- `fwpuclnt!FwpmIPsecTunnelAdd2` at `0x18003d97c`
- `fwpuclnt!FwpmIPsecTunnelAdd2` at `0x18003d768`
- `fwpuclnt!FwpmIPsecTunnelAdd2` at `0x18003d97c`
- `RPCRT4!UuidCreate` at `0x18003d694`
- `RPCRT4!UuidCreate` at `0x18003d6ac`
- `RPCRT4!UuidCreate` at `0x18003d852`
- `RPCRT4!UuidCreate` at `0x18003d888`
- `RPCRT4!UuidCreate` at `0x18003d694`
- `RPCRT4!UuidCreate` at `0x18003d6ac`
- `RPCRT4!UuidCreate` at `0x18003d852`
- `RPCRT4!UuidCreate` at `0x18003d888`
- `WS2_32!__imp_ntohl` at `0x18003d720`
- `WS2_32!__imp_ntohl` at `0x18003d732`
- `WS2_32!__imp_ntohl` at `0x18003d720`
- `WS2_32!__imp_ntohl` at `0x18003d732`

## string_xrefs

- `0x18003d87b`: `UuidCreate for V4 main-mode failed: %d`
- `0x18003d6d5`: `UuidCreate V4 quick-mode failed: %d`
- `0x18003d8ae`: `UuidCreate V6 quick-mode failed: %d`

## pseudocode

```c
__int64 __fastcall ServerBFEHandler::PlumbPolicyForRemoteIpAddr(
        struct _ROUTER_IP_ADDRESS *a1,
        struct _ROUTER_IP_ADDRESS *a2,
        struct IKEEXT_POLICY2_ *a3,
        struct IPSEC_TUNNEL_POLICY2_ *a4,
        struct _GUID *a5,
        struct _GUID *a6,
        struct _GUID *a7,
        struct _GUID *a8)
{
  char v12; // al
  unsigned int BfeHandle; // eax
  unsigned int v14; // ebx
  BOOL v15; // esi
  const wchar_t *v16; // rax
  const wchar_t *v17; // rax
  struct _GUID *v18; // rcx
  struct _GUID *v19; // rcx
  BOOL v20; // esi
  const wchar_t *v21; // rax
  unsigned int v22; // eax
  const wchar_t *v23; // rax
  unsigned int v25; // [rsp+40h] [rbp-C0h] BYREF
  void *v26; // [rsp+48h] [rbp-B8h] BYREF
  struct IKEEXT_POLICY2_ *v27; // [rsp+50h] [rbp-B0h]
  struct _GUID *v28; // [rsp+58h] [rbp-A8h]
  struct _GUID *v29; // [rsp+60h] [rbp-A0h]
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int128 v32; // [rsp+80h] [rbp-80h]
  __int64 v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+98h] [rbp-68h]
  int v35; // [rsp+9Ch] [rbp-64h]
  UUID Uuid; // [rsp+A0h] [rbp-60h] BYREF
  const wchar_t *v37; // [rsp+B0h] [rbp-50h]
  int v38; // [rsp+E0h] [rbp-20h]
  struct IKEEXT_POLICY2_ *v39; // [rsp+E8h] [rbp-18h]
  UUID v40; // [rsp+100h] [rbp+0h] BYREF
  const wchar_t *v41; // [rsp+110h] [rbp+10h]
  int v42; // [rsp+140h] [rbp+40h]
  struct IPSEC_TUNNEL_POLICY2_ *v43; // [rsp+148h] [rbp+48h]
  UUID v44; // [rsp+160h] [rbp+60h] BYREF
  const wchar_t *v45; // [rsp+170h] [rbp+70h]
  int v46; // [rsp+1A0h] [rbp+A0h]
  struct IPSEC_TUNNEL_POLICY2_ *v47; // [rsp+1A8h] [rbp+A8h]
  UUID v48; // [rsp+1C0h] [rbp+C0h] BYREF
  const wchar_t *v49; // [rsp+1D0h] [rbp+D0h]
  int v50; // [rsp+200h] [rbp+100h]
  struct IKEEXT_POLICY2_ *v51; // [rsp+208h] [rbp+108h]
  int v52; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v53[2044]; // [rsp+224h] [rbp+124h] BYREF

  v27 = a3;
  v28 = a5;
  v29 = a7;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
  }
  v25 = 0;
  Uuid.Data1 = 0;
  memset_0(&Uuid.Data2, 0, 0x54u);
  v48.Data1 = 0;
  memset_0(&v48.Data2, 0, 0x54u);
  v40.Data1 = 0;
  memset_0(&v40.Data2, 0, 0x54u);
  v44.Data1 = 0;
  memset_0(&v44.Data2, 0, 0x54u);
  v26 = 0;
  v52 = 0;
  memset_0(v53, 0, sizeof(v53));
  v31 = 0;
  v30 = 0;
  v32 = 0;
  v33 = 0;
  v34 = -1;
  v35 = 0;
  v12 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v30,
      L"ServerBFEHandler::PlumbPolicyForRemoteIpAddr",
      &v25,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v12 = byte_1800AA941;
  }
  if ( a3 && a4 )
  {
    BfeHandle = BFEHandler::GetBfeHandle(&v26);
    v14 = BfeHandle;
    v25 = BfeHandle;
    if ( BfeHandle )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_75;
      LOWORD(v52) = 0;
      FormatRRASErrorString(&v52, L"GetBfeHandle failed: %d", BfeHandle);
      goto LABEL_55;
    }
    memset_0(&Uuid, 0, 0x58u);
    memset_0(&v48, 0, 0x58u);
    memset_0(&v40, 0, 0x58u);
    memset_0(&v44, 0, 0x58u);
    if ( ServerBFEHandler::v4Installed && (!a2 || *(_WORD *)a2 == 2) )
    {
      v15 = 0;
      if ( a1 )
        v15 = *(_WORD *)a1 == 2;
      if ( a2 )
      {
        v16 = L"IKEv2 Server Main mode IPsec tunnel policy (v4) (specificDestIPAddr to *)";
        if ( v15 )
          v16 = L"IKEv2 Server Main mode IPsec tunnel policy (v4) (specificDestIPAddr to specificSrcIPAddr)";
      }
      else
      {
        v16 = L"IKEv2 Server Main mode IPsec tunnel policy (v4) (* to *)";
      }
      v37 = v16;
      v38 = 10;
      v39 = v27;
      v14 = UuidCreate(&Uuid);
      v25 = v14;
      if ( v14 )
      {
LABEL_49:
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_75;
        LOWORD(v52) = 0;
        FormatRRASErrorString(&v52, L"UuidCreate for V4 main-mode failed: %d", v14);
        goto LABEL_55;
      }
      v14 = UuidCreate(&v40);
      v25 = v14;
      if ( v14 )
      {
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_75;
        LOWORD(v52) = 0;
        FormatRRASErrorString(&v52, L"UuidCreate V4 quick-mode failed: %d", v14);
        goto LABEL_55;
      }
      if ( a2 )
      {
        v17 = L"IKEv2 Server Quick mode IPsec tunnel policy (v4)(specificDestIPAddr to *)";
        if ( v15 )
          v17 = L"IKEv2 Server Quick mode IPsec tunnel policy (v4)(specificDestIPAddr to specificSrcIPAddr)";
      }
      else
      {
        v17 = L"IKEv2 Server Quick mode IPsec tunnel policy (v4)(* to *)";
      }
      v41 = v17;
      v42 = 9;
      v43 = a4;
      *((_DWORD *)a4 + 4) = 0;
      if ( a2 )
      {
        *((_DWORD *)a4 + 9) = ntohl(*((_DWORD *)a2 + 1));
        if ( v15 )
          *((_DWORD *)a4 + 5) = ntohl(*((_DWORD *)a1 + 1));
      }
      v14 = FwpmIPsecTunnelAdd2(v26, 2, &Uuid, &v40, 0, 0, &FWPM_KEYING_MODULE_IKEV2, 0);
      v25 = v14;
      if ( v14 )
      {
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_75;
        LOWORD(v52) = 0;
        FormatRRASErrorString(&v52, L"FwpmIPsecTunnelAdd2 V4 failed: %d", v14);
        goto LABEL_55;
      }
      v18 = v28;
      if ( v28 )
      {
        v28->Data1 = Uuid.Data1;
        *(_QWORD *)&v18->Data2 = *(_QWORD *)&Uuid.Data2;
        *(_DWORD *)&v18->Data4[4] = *(_DWORD *)&Uuid.Data4[4];
      }
      v19 = v29;
      if ( v29 )
      {
        v29->Data1 = v40.Data1;
        *(_QWORD *)&v19->Data2 = *(_QWORD *)&v40.Data2;
        *(_DWORD *)&v19->Data4[4] = *(_DWORD *)&v40.Data4[4];
      }
    }
    if ( !ServerBFEHandler::v6Installed || a2 && *(_WORD *)a2 != 23 )
      goto LABEL_75;
    v20 = 0;
    if ( a1 )
      v20 = *(_WORD *)a1 == 23;
    if ( a2 )
    {
      v21 = L"IKEv2 Server Main mode IPsec tunnel policy (v6) (specificDestIPAddr to *)";
      if ( v20 )
        v21 = L"IKEv2 Server Main mode IPsec tunnel policy (v6) (specificDestIPAddr to specificSrcIPAddr)";
    }
    else
    {
      v21 = L"IKEv2 Server Main mode IPsec tunnel policy (v6) (* to *)";
    }
    v49 = v21;
    v50 = 10;
    v51 = v27;
    v14 = UuidCreate(&v48);
    v25 = v14;
    if ( v14 )
      goto LABEL_49;
    v22 = UuidCreate(&v44);
    v14 = v22;
    v25 = v22;
    if ( v22 )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_75;
      LOWORD(v52) = 0;
      FormatRRASErrorString(&v52, L"UuidCreate V6 quick-mode failed: %d", v22);
      goto LABEL_55;
    }
    if ( a2 )
    {
      v23 = L"IKEv2 Server Quick mode IPsec tunnel policy (v6)(specificDestIPAddr to *)";
      if ( v20 )
        v23 = L"IKEv2 Server Quick mode IPsec tunnel policy (v6)(specificDestIPAddr to specificSrcIPAddr)";
    }
    else
    {
      v23 = L"IKEv2 Server Quick mode IPsec tunnel policy (v6)(* to *)";
    }
    v45 = v23;
    v46 = 9;
    v47 = a4;
    *((_DWORD *)a4 + 4) = 1;
    if ( a2 )
    {
      *(_OWORD *)((char *)a4 + 36) = *(_OWORD *)((char *)a2 + 4);
      if ( v20 )
        *(_OWORD *)((char *)a4 + 20) = *(_OWORD *)((char *)a1 + 4);
    }
    v14 = FwpmIPsecTunnelAdd2(v26, 2, &v48, &v44, 0, 0, &FWPM_KEYING_MODULE_IKEV2, 0);
    v25 = v14;
    if ( v14 )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_75;
      LOWORD(v52) = 0;
      FormatRRASErrorString(&v52, L"FwpmIPsecTunnelAdd2 V6 failed: %d", v14);
LABEL_55:
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v52);
      v14 = v25;
      goto LABEL_75;
    }
    if ( a8 )
      *a8 = v44;
    if ( a6 )
      *a6 = v48;
  }
  else
  {
    if ( (v12 & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasVpnIkeTraceError,
        L"PlumbPolicyForRemoteIpAddr: invalid input parameters");
    v14 = 87;
    v25 = 87;
  }
LABEL_75:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids, v14);
    v14 = v25;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v30);
  return v14;
}

```

## disassembly

```asm
0x18003d434  push    rbp
0x18003d436  push    rbx
0x18003d437  push    rsi
0x18003d438  push    rdi
0x18003d439  push    r12
0x18003d43b  push    r13
0x18003d43d  push    r14
0x18003d43f  push    r15
0x18003d441  lea     rbp, [rsp-938h]
0x18003d449  sub     rsp, 0A38h
0x18003d450  mov     rax, cs:__security_cookie
0x18003d457  xor     rax, rsp
0x18003d45a  mov     [rbp+970h+var_50], rax
0x18003d461  mov     r14, r9
0x18003d464  mov     rbx, r8
0x18003d467  mov     [rsp+0A70h+var_A20], rbx
0x18003d46c  mov     rdi, rdx
0x18003d46f  mov     r15, rcx
0x18003d472  mov     rax, [rbp+970h+arg_20]
0x18003d479  mov     [rsp+0A70h+var_A18], rax
0x18003d47e  mov     r12, [rbp+970h+arg_28]
0x18003d485  mov     rax, [rbp+970h+arg_30]
0x18003d48c  mov     [rsp+0A70h+var_A10], rax
0x18003d491  mov     r13, [rbp+970h+arg_38]
0x18003d498  lea     rax, WPP_GLOBAL_Control
0x18003d49f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d4a6  cmp     rcx, rax
0x18003d4a9  jz      short loc_18003D4CC
0x18003d4ab  test    byte ptr [rcx+1Ch], 1
0x18003d4af  jz      short loc_18003D4CC
0x18003d4b1  cmp     byte ptr [rcx+19h], 6
0x18003d4b5  jb      short loc_18003D4CC
0x18003d4b7  mov     edx, 2Fh ; '/'
0x18003d4bc  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x18003d4c3  mov     rcx, [rcx+10h]
0x18003d4c7  call    WPP_SF_
0x18003d4cc  mov     [rsp+0A70h+var_A30], 0
0x18003d4d4  mov     [rbp+970h+Uuid.Data1], 0
0x18003d4db  mov     esi, 54h ; 'T'
0x18003d4e0  mov     r8d, esi; Size
0x18003d4e3  xor     edx, edx; Val
0x18003d4e5  lea     rcx, [rbp+970h+Uuid.Data2]; void *
0x18003d4e9  call    memset_0
0x18003d4ee  mov     [rbp+970h+var_8B0.Data1], 0
0x18003d4f8  mov     r8d, esi; Size
0x18003d4fb  xor     edx, edx; Val
0x18003d4fd  lea     rcx, [rbp+970h+var_8B0.Data2]; void *
0x18003d504  call    memset_0
0x18003d509  mov     [rbp+970h+var_970.Data1], 0
0x18003d510  mov     r8d, esi; Size
0x18003d513  xor     edx, edx; Val
0x18003d515  lea     rcx, [rbp+970h+var_970.Data2]; void *
0x18003d519  call    memset_0
0x18003d51e  mov     [rbp+970h+var_910.Data1], 0
0x18003d525  mov     r8d, esi; Size
0x18003d528  xor     edx, edx; Val
0x18003d52a  lea     rcx, [rbp+970h+var_910.Data2]; void *
0x18003d52e  call    memset_0
0x18003d533  xor     esi, esi
0x18003d535  mov     [rsp+0A70h+var_A28], rsi
0x18003d53a  mov     [rbp+970h+var_850], esi
0x18003d540  xor     edx, edx; Val
0x18003d542  mov     r8d, 7FCh; Size
0x18003d548  lea     rcx, [rbp+970h+var_84C]; void *
0x18003d54f  call    memset_0
0x18003d554  xorps   xmm0, xmm0
0x18003d557  movdqu  [rsp+0A70h+var_A00], xmm0
0x18003d55d  mov     [rsp+0A70h+var_A08], rsi
0x18003d562  xorps   xmm1, xmm1
0x18003d565  movdqu  [rbp+970h+var_9F0], xmm1
0x18003d56a  mov     [rbp+970h+var_9E0], rsi
0x18003d56e  mov     [rbp+970h+var_9D8], 0FFFFFFFFh
0x18003d575  mov     [rbp+970h+var_9D4], esi
0x18003d578  mov     al, cs:byte_1800AA941
0x18003d57e  test    al, 8
0x18003d580  jz      short loc_18003D5A5
0x18003d582  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18003d589  lea     r8, [rsp+0A70h+var_A30]; unsigned int *
0x18003d58e  lea     rdx, aServerbfehandl_12; "ServerBFEHandler::PlumbPolicyForRemoteI"...
0x18003d595  lea     rcx, [rsp+0A70h+var_A08]; this
0x18003d59a  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18003d59f  mov     al, cs:byte_1800AA941
0x18003d5a5  test    rbx, rbx
0x18003d5a8  jz      loc_18003D9FA
0x18003d5ae  test    r14, r14
0x18003d5b1  jz      loc_18003D9FA
0x18003d5b7  lea     rcx, [rsp+0A70h+var_A28]; void **
0x18003d5bc  call    ?GetBfeHandle@BFEHandler@@SAKPEAPEAX@Z; BFEHandler::GetBfeHandle(void * *)
0x18003d5c1  mov     ebx, eax
0x18003d5c3  mov     [rsp+0A70h+var_A30], eax
0x18003d5c7  test    eax, eax
0x18003d5c9  jz      short loc_18003D5EB
0x18003d5cb  test    cs:byte_1800AA941, 4
0x18003d5d2  jz      loc_18003DA21
0x18003d5d8  mov     word ptr [rbp+970h+var_850], si
0x18003d5df  lea     rdx, aGetbfehandleFa; "GetBfeHandle failed: %d"
0x18003d5e6  jmp     loc_18003D8B5
0x18003d5eb  mov     esi, 58h ; 'X'
0x18003d5f0  mov     r8d, esi; Size
0x18003d5f3  xor     edx, edx; Val
0x18003d5f5  lea     rcx, [rbp+970h+Uuid]; void *
0x18003d5f9  call    memset_0
0x18003d5fe  mov     r8d, esi; Size
0x18003d601  xor     edx, edx; Val
0x18003d603  lea     rcx, [rbp+970h+var_8B0]; void *
0x18003d60a  call    memset_0
0x18003d60f  mov     r8d, esi; Size
0x18003d612  xor     edx, edx; Val
0x18003d614  lea     rcx, [rbp+970h+var_970]; void *
0x18003d618  call    memset_0
0x18003d61d  mov     r8d, esi; Size
0x18003d620  xor     edx, edx; Val
0x18003d622  lea     rcx, [rbp+970h+var_910]; void *
0x18003d626  call    memset_0
0x18003d62b  lea     eax, [rsi-56h]
0x18003d62e  cmp     cs:?v4Installed@ServerBFEHandler@@1HA, 0; int ServerBFEHandler::v4Installed
0x18003d635  jz      loc_18003D7DB
0x18003d63b  test    rdi, rdi
0x18003d63e  jz      short loc_18003D649
0x18003d640  cmp     [rdi], ax
0x18003d643  jnz     loc_18003D7DB
0x18003d649  xor     esi, esi
0x18003d64b  test    r15, r15
0x18003d64e  jz      short loc_18003D65A
0x18003d650  cmp     ax, [r15]
0x18003d654  lea     eax, [rsi+1]
0x18003d657  cmovz   esi, eax
0x18003d65a  test    rdi, rdi
0x18003d65d  jnz     short loc_18003D668
0x18003d65f  lea     rax, aIkev2ServerMai_2; "IKEv2 Server Main mode IPsec tunnel pol"...
0x18003d666  jmp     short loc_18003D67C
0x18003d668  lea     rax, aIkev2ServerMai; "IKEv2 Server Main mode IPsec tunnel pol"...
0x18003d66f  lea     rcx, aIkev2ServerMai_3; "IKEv2 Server Main mode IPsec tunnel pol"...
0x18003d676  test    esi, esi
0x18003d678  cmovnz  rax, rcx
0x18003d67c  mov     [rbp+970h+var_9C0], rax
0x18003d680  mov     [rbp+970h+var_990], 0Ah
0x18003d687  mov     rax, [rsp+0A70h+var_A20]
0x18003d68c  mov     [rbp+970h+var_988], rax
0x18003d690  lea     rcx, [rbp+970h+Uuid]; Uuid
0x18003d694  call    cs:__imp_UuidCreate
0x18003d69a  mov     ebx, eax
0x18003d69c  mov     [rsp+0A70h+var_A30], eax
0x18003d6a0  test    eax, eax
0x18003d6a2  jnz     loc_18003D862
0x18003d6a8  lea     rcx, [rbp+970h+var_970]; Uuid
0x18003d6ac  call    cs:__imp_UuidCreate
0x18003d6b2  mov     ebx, eax
0x18003d6b4  mov     [rsp+0A70h+var_A30], eax
0x18003d6b8  test    eax, eax
0x18003d6ba  jz      short loc_18003D6E1
0x18003d6bc  test    cs:byte_1800AA941, 4
0x18003d6c3  jz      loc_18003DA21
0x18003d6c9  xor     eax, eax
0x18003d6cb  mov     word ptr [rbp+970h+var_850], ax
0x18003d6d2  mov     r8d, ebx
0x18003d6d5  lea     rdx, aUuidcreateV4Qu; "UuidCreate V4 quick-mode failed: %d"
0x18003d6dc  jmp     loc_18003D8B8
0x18003d6e1  xor     ebx, ebx
0x18003d6e3  test    rdi, rdi
0x18003d6e6  jnz     short loc_18003D6F1
0x18003d6e8  lea     rax, aIkev2ServerQui_4; "IKEv2 Server Quick mode IPsec tunnel po"...
0x18003d6ef  jmp     short loc_18003D705
0x18003d6f1  lea     rax, aIkev2ServerQui_1; "IKEv2 Server Quick mode IPsec tunnel po"...
0x18003d6f8  lea     rcx, aIkev2ServerQui_3; "IKEv2 Server Quick mode IPsec tunnel po"...
0x18003d6ff  test    esi, esi
0x18003d701  cmovnz  rax, rcx
0x18003d705  mov     [rbp+970h+var_960], rax
0x18003d709  mov     [rbp+970h+var_930], 9
0x18003d710  mov     [rbp+970h+var_928], r14
0x18003d714  mov     [r14+10h], ebx
0x18003d718  test    rdi, rdi
0x18003d71b  jz      short loc_18003D73C
0x18003d71d  mov     ecx, [rdi+4]; netlong
0x18003d720  call    cs:__imp_ntohl
0x18003d726  mov     [r14+24h], eax
0x18003d72a  test    esi, esi
0x18003d72c  jz      short loc_18003D73C
0x18003d72e  mov     ecx, [r15+4]; netlong
0x18003d732  call    cs:__imp_ntohl
0x18003d738  mov     [r14+14h], eax
0x18003d73c  mov     [rsp+0A70h+var_A38], rbx
0x18003d741  lea     rax, FWPM_KEYING_MODULE_IKEV2
0x18003d748  mov     [rsp+0A70h+var_A40], rax
0x18003d74d  mov     [rsp+0A70h+var_A48], rbx
0x18003d752  mov     [rsp+0A70h+var_A50], ebx
0x18003d756  lea     r9, [rbp+970h+var_970]
0x18003d75a  lea     r8, [rbp+970h+Uuid]
0x18003d75e  mov     edx, 2
0x18003d763  mov     rcx, [rsp+0A70h+var_A28]
0x18003d768  call    cs:__imp_FwpmIPsecTunnelAdd2
0x18003d76e  mov     ebx, eax
0x18003d770  mov     [rsp+0A70h+var_A30], eax
0x18003d774  test    eax, eax
0x18003d776  jz      short loc_18003D79D
0x18003d778  test    cs:byte_1800AA941, 4
0x18003d77f  jz      loc_18003DA21
0x18003d785  xor     eax, eax
0x18003d787  mov     word ptr [rbp+970h+var_850], ax
0x18003d78e  mov     r8d, ebx
0x18003d791  lea     rdx, aFwpmipsectunne; "FwpmIPsecTunnelAdd2 V4 failed: %d"
0x18003d798  jmp     loc_18003D8B8
0x18003d79d  mov     rcx, [rsp+0A70h+var_A18]
0x18003d7a2  test    rcx, rcx
0x18003d7a5  jz      short loc_18003D7BC
0x18003d7a7  mov     eax, [rbp+970h+Uuid.Data1]
0x18003d7aa  mov     [rcx], eax
0x18003d7ac  movsd   xmm0, qword ptr [rbp+970h+Uuid.Data2]
0x18003d7b1  movsd   qword ptr [rcx+4], xmm0
0x18003d7b6  mov     eax, dword ptr [rbp+970h+Uuid.Data4+4]
0x18003d7b9  mov     [rcx+0Ch], eax
0x18003d7bc  mov     rcx, [rsp+0A70h+var_A10]
0x18003d7c1  test    rcx, rcx
0x18003d7c4  jz      short loc_18003D7DB
0x18003d7c6  mov     eax, [rbp+970h+var_970.Data1]
0x18003d7c9  mov     [rcx], eax
0x18003d7cb  movsd   xmm0, qword ptr [rbp+970h+var_970.Data2]
0x18003d7d0  movsd   qword ptr [rcx+4], xmm0
0x18003d7d5  mov     eax, dword ptr [rbp+970h+var_970.Data4+4]
0x18003d7d8  mov     [rcx+0Ch], eax
0x18003d7db  cmp     cs:?v6Installed@ServerBFEHandler@@1HA, 0; int ServerBFEHandler::v6Installed
0x18003d7e2  jz      loc_18003DA21
0x18003d7e8  mov     eax, 17h
0x18003d7ed  test    rdi, rdi
0x18003d7f0  jz      short loc_18003D7FB
0x18003d7f2  cmp     [rdi], ax
0x18003d7f5  jnz     loc_18003DA21
0x18003d7fb  xor     esi, esi
0x18003d7fd  test    r15, r15
0x18003d800  jz      short loc_18003D80C
0x18003d802  cmp     ax, [r15]
0x18003d806  lea     eax, [rsi+1]
0x18003d809  cmovz   esi, eax
0x18003d80c  test    rdi, rdi
0x18003d80f  jnz     short loc_18003D81A
0x18003d811  lea     rax, aIkev2ServerMai_0; "IKEv2 Server Main mode IPsec tunnel pol"...
0x18003d818  jmp     short loc_18003D82E
0x18003d81a  lea     rax, aIkev2ServerMai_1; "IKEv2 Server Main mode IPsec tunnel pol"...
0x18003d821  lea     rcx, aIkev2ServerMai_4; "IKEv2 Server Main mode IPsec tunnel pol"...
0x18003d828  test    esi, esi
0x18003d82a  cmovnz  rax, rcx
0x18003d82e  mov     [rbp+970h+var_8A0], rax
0x18003d835  mov     [rbp+970h+var_870], 0Ah
0x18003d83f  mov     rax, [rsp+0A70h+var_A20]
0x18003d844  mov     [rbp+970h+var_868], rax
0x18003d84b  lea     rcx, [rbp+970h+var_8B0]; Uuid
0x18003d852  call    cs:__imp_UuidCreate
0x18003d858  mov     ebx, eax
0x18003d85a  mov     [rsp+0A70h+var_A30], eax
0x18003d85e  test    eax, eax
0x18003d860  jz      short loc_18003D884
0x18003d862  test    cs:byte_1800AA941, 4
0x18003d869  jz      loc_18003DA21
0x18003d86f  xor     eax, eax
0x18003d871  mov     word ptr [rbp+970h+var_850], ax
0x18003d878  mov     r8d, ebx
0x18003d87b  lea     rdx, aUuidcreateForV; "UuidCreate for V4 main-mode failed: %d"
0x18003d882  jmp     short loc_18003D8B8
0x18003d884  lea     rcx, [rbp+970h+var_910]; Uuid
0x18003d888  call    cs:__imp_UuidCreate
0x18003d88e  mov     ebx, eax
0x18003d890  mov     [rsp+0A70h+var_A30], eax
0x18003d894  xor     edx, edx
0x18003d896  test    eax, eax
0x18003d898  jz      short loc_18003D8F0
0x18003d89a  test    cs:byte_1800AA941, 4
0x18003d8a1  jz      loc_18003DA21
0x18003d8a7  mov     word ptr [rbp+970h+var_850], dx
0x18003d8ae  lea     rdx, aUuidcreateV6Qu; "UuidCreate V6 quick-mode failed: %d"
0x18003d8b5  mov     r8d, eax
0x18003d8b8  lea     rcx, [rbp+970h+var_850]
0x18003d8bf  call    FormatRRASErrorString
0x18003d8c4  test    cs:byte_1800AA941, 4
0x18003d8cb  jz      short loc_18003D8E7
0x18003d8cd  lea     r8, [rbp+970h+var_850]
0x18003d8d4  lea     rdx, RasVpnIkeTraceError
0x18003d8db  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003d8e2  call    McTemplateU0z_EventWriteTransfer
0x18003d8e7  mov     ebx, [rsp+0A70h+var_A30]
0x18003d8eb  jmp     loc_18003DA21
0x18003d8f0  test    rdi, rdi
0x18003d8f3  jnz     short loc_18003D8FE
0x18003d8f5  lea     rax, aIkev2ServerQui_2; "IKEv2 Server Quick mode IPsec tunnel po"...
0x18003d8fc  jmp     short loc_18003D912
0x18003d8fe  lea     rax, aIkev2ServerQui_0; "IKEv2 Server Quick mode IPsec tunnel po"...
0x18003d905  lea     rcx, aIkev2ServerQui; "IKEv2 Server Quick mode IPsec tunnel po"...
0x18003d90c  test    esi, esi
0x18003d90e  cmovnz  rax, rcx
0x18003d912  mov     [rbp+970h+var_900], rax
0x18003d916  mov     [rbp+970h+var_8D0], 9
0x18003d920  mov     [rbp+970h+var_8C8], r14
0x18003d927  mov     dword ptr [r14+10h], 1
0x18003d92f  test    rdi, rdi
0x18003d932  jz      short loc_18003D94D
0x18003d934  movups  xmm0, xmmword ptr [rdi+4]
0x18003d938  movdqu  xmmword ptr [r14+24h], xmm0
0x18003d93e  test    esi, esi
0x18003d940  jz      short loc_18003D94D
0x18003d942  movups  xmm0, xmmword ptr [r15+4]
0x18003d947  movdqu  xmmword ptr [r14+14h], xmm0
  ... truncated ...
```
