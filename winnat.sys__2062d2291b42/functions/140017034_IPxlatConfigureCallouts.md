# IPxlatConfigureCallouts

- ea: `0x140017034`
- end: `0x1400177af`
- name: `IPxlatConfigureCallouts`
- size: `1915`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400162c0`
- `0x140016334`
- `0x140036cac`

## callees

- `0x140016fdc`
- `0x140017034`
- `0x14001f320`
- `0x14001f980`
- `0x14002e008`
- `0x14002e040`
- `0x14002e4b0`

## import_xrefs

- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400171ee`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140017325`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x14001747e`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400174ae`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140017691`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400176c1`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400176f1`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140017739`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400171ee`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140017325`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x14001747e`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400174ae`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140017691`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400176c1`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400176f1`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140017739`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x1400171b2`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x1400172e9`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x14001743e`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x1400175c1`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x1400171b2`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x1400172e9`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x14001743e`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x1400175c1`
- `fwpkclnt!FwpmBfeStateGet0` at `0x1400170bf`
- `fwpkclnt!FwpmBfeStateGet0` at `0x1400170bf`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x14001733d`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x140017496`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x1400174c6`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x1400176a9`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x1400176d9`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x140017709`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x140017751`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x14001733d`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x140017496`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x1400174c6`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x1400176a9`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x1400176d9`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x140017709`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x140017751`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x14001723b`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x14001738c`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x140017515`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x140017634`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x14001723b`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x14001738c`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x140017515`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x140017634`
- `fwpkclnt!FwpmEngineClose0` at `0x140017762`
- `fwpkclnt!FwpmEngineClose0` at `0x140017762`
- `fwpkclnt!FwpmEngineOpen0` at `0x140017109`
- `fwpkclnt!FwpmEngineOpen0` at `0x140017109`

## string_xrefs

- `0x1400172ca`: `Filters incoming IPv6 packets into synthetic IPv4 packets`
- `0x140017371`: `Sub layer for filtering incoming IPv6 packets into synthetic IPv4 packets`

## pseudocode

```c
__int64 __fastcall IPxlatConfigureCallouts(char a1)
{
  __int64 v2; // rcx
  __int64 v3; // r9
  unsigned int v4; // ebx
  NTSTATUS v5; // eax
  NTSTATUS v6; // eax
  __int64 v7; // rdx
  __int128 *v8; // rdx
  NTSTATUS v9; // eax
  __int64 v10; // rdx
  NTSTATUS v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  NTSTATUS v14; // eax
  __int64 v15; // rdx
  int IsEnabledDeviceUsageNoInline; // eax
  HANDLE engineHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v20; // [rsp+48h] [rbp-B8h]
  __int128 v21; // [rsp+58h] [rbp-A8h]
  FWPM_SUBLAYER0 subLayer; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v23[6]; // [rsp+C0h] [rbp-40h] BYREF

  engineHandle = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  memset(v23, 0, 0x58u);
  memset(&subLayer, 0, sizeof(subLayer));
  if ( (xmmword_1400272E0 & 2) != 0 )
  {
    LOBYTE(v3) = a1;
    WPP_SF_c(v2, 10, WPP_b58024cfe01b3143f1c8b927d5346b48_Traceguids, v3);
  }
  if ( FwpmBfeStateGet0() != FWPM_SERVICE_RUNNING )
  {
    if ( (xmmword_1400272D0 & 2) != 0 )
      WPP_SF_(513, 11, WPP_b58024cfe01b3143f1c8b927d5346b48_Traceguids);
    v4 = -1073741661;
    goto LABEL_55;
  }
  v5 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  v4 = v5;
  if ( v5 >= 0 )
  {
    if ( !a1 )
    {
      FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT);
      FwpmSubLayerDeleteByKey0(engineHandle, &IPXLAT_WFP_OUTBOUND_IPV4_SUBLAYER);
      FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &IPXLAT_WFP_INBOUND_IPV6_LAYER_CALLOUT);
      FwpmSubLayerDeleteByKey0(engineHandle, &IPXLAT_WFP_INBOUND_IPV6_SUBLAYER);
      FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &IPXLAT_WFP_FORWARD_IPV4_LAYER_CALLOUT);
      FwpmSubLayerDeleteByKey0(engineHandle, &IPXLAT_WFP_FORWARD_IPV4_SUBLAYER);
      if ( (Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_featureState & 0x10) != 0 )
        IsEnabledDeviceUsageNoInline = Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_featureState & 1;
      else
        IsEnabledDeviceUsageNoInline = Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_IsEnabledDeviceUsageNoInline();
      if ( IsEnabledDeviceUsageNoInline )
      {
        FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &IPXLAT_WFP_OUTBOUND_ETHERNET_LAYER_CALLOUT);
        FwpmSubLayerDeleteByKey0(engineHandle, &IPXLAT_WFP_OUTBOUND_ETHERNET_SUBLAYER);
      }
      goto LABEL_54;
    }
    *((_QWORD *)&v21 + 1) = 0;
    *((_QWORD *)&v20 + 1) = IPxlatOutboundIPv4Callout;
    *(_QWORD *)&v21 = IPxlatNotifyCallout;
    v19 = IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT;
    *(_QWORD *)&v23[1] = L"IPxlat Outbound IPv4 filter";
    v23[0] = IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT;
    *((_QWORD *)&v23[1] + 1) = L"Filters outgoing IPv4 packets into synthetic IPv6 packets";
    v23[4] = FWPM_LAYER_OUTBOUND_IPPACKET_V4;
    v6 = FwpiCalloutRegisterAndAddWithoutDevice0(engineHandle, &v19, v23, 0, 0);
    v4 = v6;
    if ( v6 < 0 )
    {
      if ( (xmmword_1400272D0 & 2) == 0 )
      {
LABEL_15:
        v8 = &IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT;
LABEL_16:
        FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, v8);
LABEL_54:
        FwpmEngineClose0(engineHandle);
        goto LABEL_55;
      }
      v7 = 13;
LABEL_14:
      WPP_SF_d(513, v7, WPP_b58024cfe01b3143f1c8b927d5346b48_Traceguids, (unsigned int)v6);
      goto LABEL_15;
    }
    subLayer.displayData.name = L"IPxlat Outbound IPv4 sub layer";
    subLayer.flags = 0;
    subLayer.displayData.description = L"Sub layer for filtering outgoing IPv4 packets into synthetic IPv6 packets";
    subLayer.weight = 0x7FFF;
    subLayer.subLayerKey = IPXLAT_WFP_OUTBOUND_IPV4_SUBLAYER;
    v6 = FwpmSubLayerAdd0(engineHandle, &subLayer, 0);
    v4 = v6;
    if ( v6 < 0 )
    {
      if ( (xmmword_1400272D0 & 2) == 0 )
        goto LABEL_15;
      v7 = 14;
      goto LABEL_14;
    }
    *(_QWORD *)&v20 = 0;
    memset(v23, 0, 0x58u);
    memset(&subLayer, 0, sizeof(subLayer));
    *((_QWORD *)&v20 + 1) = &IPxlatInboundIPv6Callout;
    *((_QWORD *)&v21 + 1) = 0;
    *(_QWORD *)&v21 = IPxlatNotifyCallout;
    v19 = IPXLAT_WFP_INBOUND_IPV6_LAYER_CALLOUT;
    *(_QWORD *)&v23[1] = L"IPxlat Inbound IPv6 filter";
    v23[0] = IPXLAT_WFP_INBOUND_IPV6_LAYER_CALLOUT;
    *((_QWORD *)&v23[1] + 1) = L"Filters incoming IPv6 packets into synthetic IPv4 packets";
    v23[4] = FWPM_LAYER_INBOUND_IPPACKET_V6;
    v9 = FwpiCalloutRegisterAndAddWithoutDevice0(engineHandle, &v19, v23, 0, 0);
    v4 = v9;
    if ( v9 < 0 )
    {
      if ( (xmmword_1400272D0 & 2) == 0 )
      {
LABEL_24:
        FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT);
        FwpmSubLayerDeleteByKey0(engineHandle, &IPXLAT_WFP_OUTBOUND_IPV4_SUBLAYER);
        v8 = &IPXLAT_WFP_INBOUND_IPV6_LAYER_CALLOUT;
        goto LABEL_16;
      }
      v10 = 15;
LABEL_23:
      WPP_SF_d(513, v10, WPP_b58024cfe01b3143f1c8b927d5346b48_Traceguids, (unsigned int)v9);
      goto LABEL_24;
    }
    subLayer.displayData.name = L"IPxlat Inbound IPv6 sub layer";
    subLayer.flags = 0;
    subLayer.displayData.description = L"Sub layer for filtering incoming IPv6 packets into synthetic IPv4 packets";
    subLayer.subLayerKey = IPXLAT_WFP_INBOUND_IPV6_SUBLAYER;
    subLayer.weight = 0x7FFF;
    v9 = FwpmSubLayerAdd0(engineHandle, &subLayer, 0);
    v4 = v9;
    if ( v9 < 0 )
    {
      if ( (xmmword_1400272D0 & 2) == 0 )
        goto LABEL_24;
      v10 = 16;
      goto LABEL_23;
    }
    *(_QWORD *)&v20 = 0;
    memset(v23, 0, 0x58u);
    memset(&subLayer, 0, sizeof(subLayer));
    *((_QWORD *)&v20 + 1) = IPxlatForwardIPv4Callout;
    *((_QWORD *)&v21 + 1) = 0;
    *(_QWORD *)&v21 = IPxlatNotifyCallout;
    v19 = IPXLAT_WFP_FORWARD_IPV4_LAYER_CALLOUT;
    *(_QWORD *)&v23[1] = L"IPxlat Forward IPv4 filter";
    v23[0] = IPXLAT_WFP_FORWARD_IPV4_LAYER_CALLOUT;
    *((_QWORD *)&v23[1] + 1) = L"Filters forwarded IPv4 packets into synthetic IPv6 packets";
    v23[4] = FWPM_LAYER_IPFORWARD_V4;
    v11 = FwpiCalloutRegisterAndAddWithoutDevice0(engineHandle, &v19, v23, 0, 0);
    v4 = v11;
    if ( v11 < 0 )
    {
      if ( (xmmword_1400272D0 & 2) == 0 )
      {
LABEL_32:
        FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT);
        FwpmSubLayerDeleteByKey0(engineHandle, &IPXLAT_WFP_OUTBOUND_IPV4_SUBLAYER);
        FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &IPXLAT_WFP_INBOUND_IPV6_LAYER_CALLOUT);
        FwpmSubLayerDeleteByKey0(engineHandle, &IPXLAT_WFP_INBOUND_IPV6_SUBLAYER);
        v8 = &IPXLAT_WFP_FORWARD_IPV4_LAYER_CALLOUT;
        goto LABEL_16;
      }
      v12 = 17;
LABEL_31:
      WPP_SF_d(513, v12, WPP_b58024cfe01b3143f1c8b927d5346b48_Traceguids, (unsigned int)v11);
      goto LABEL_32;
    }
    subLayer.displayData.name = L"IPxlat Forward IPv4 sub layer";
    subLayer.flags = 0;
    subLayer.displayData.description = L"Sub layer for filtering forwarded IPv4 packets into synthetic IPv6 packets";
    subLayer.subLayerKey = IPXLAT_WFP_FORWARD_IPV4_SUBLAYER;
    subLayer.weight = 0x7FFF;
    v11 = FwpmSubLayerAdd0(engineHandle, &subLayer, 0);
    v4 = v11;
    if ( v11 < 0 )
    {
      if ( (xmmword_1400272D0 & 2) == 0 )
        goto LABEL_32;
      v12 = 18;
      goto LABEL_31;
    }
    if ( (Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_featureState & 0x10) != 0 )
      v13 = Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_featureState & 1;
    else
      v13 = Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_IsEnabledDeviceUsageNoInline();
    if ( !v13 )
      goto LABEL_54;
    *((_QWORD *)&v20 + 1) = IPxlatOutboundEthernetCallout;
    *((_QWORD *)&v21 + 1) = 0;
    *(_QWORD *)&v21 = IPxlatNotifyCallout;
    v19 = IPXLAT_WFP_OUTBOUND_ETHERNET_LAYER_CALLOUT;
    *(_QWORD *)&v23[1] = L"IPxlat Outbound Ethernet filter";
    v23[0] = IPXLAT_WFP_OUTBOUND_ETHERNET_LAYER_CALLOUT;
    *((_QWORD *)&v23[1] + 1) = L"Filters outgoing ethernet packets to block synthetic IPv4 DAD";
    v23[4] = FWPM_LAYER_OUTBOUND_MAC_FRAME_ETHERNET;
    v14 = FwpiCalloutRegisterAndAddWithoutDevice0(engineHandle, &v19, v23, 0, 0);
    v4 = v14;
    if ( v14 >= 0 )
    {
      subLayer.displayData.name = L"IPxlat Outbound Ethernet sub layer";
      subLayer.flags = 0;
      subLayer.displayData.description = L"Sub layer for filtering outbound ARP packets for synthentic IPv4 DAD";
      subLayer.subLayerKey = IPXLAT_WFP_OUTBOUND_ETHERNET_SUBLAYER;
      subLayer.weight = 0x7FFF;
      v14 = FwpmSubLayerAdd0(engineHandle, &subLayer, 0);
      v4 = v14;
      if ( v14 >= 0 )
      {
        v19 = 0;
        v20 = 0;
        v21 = 0;
        memset(v23, 0, 0x58u);
        memset(&subLayer, 0, sizeof(subLayer));
        goto LABEL_54;
      }
      if ( (xmmword_1400272D0 & 2) == 0 )
        goto LABEL_44;
      v15 = 20;
    }
    else
    {
      if ( (xmmword_1400272D0 & 2) == 0 )
      {
LABEL_44:
        v8 = &IPXLAT_WFP_OUTBOUND_ETHERNET_LAYER_CALLOUT;
        goto LABEL_16;
      }
      v15 = 19;
    }
    WPP_SF_d(513, v15, WPP_b58024cfe01b3143f1c8b927d5346b48_Traceguids, (unsigned int)v14);
    goto LABEL_44;
  }
  if ( (xmmword_1400272D0 & 2) != 0 )
    WPP_SF_d(513, 12, WPP_b58024cfe01b3143f1c8b927d5346b48_Traceguids, (unsigned int)v5);
LABEL_55:
  if ( (xmmword_1400272E0 & 2) != 0 )
    WPP_SF_d(1025, 21, WPP_b58024cfe01b3143f1c8b927d5346b48_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x140017034  push    rbp
0x140017036  push    rbx
0x140017037  push    rsi
0x140017038  push    rdi
0x140017039  push    r12
0x14001703b  push    r13
0x14001703d  push    r14
0x14001703f  push    r15
0x140017041  lea     rbp, [rsp-38h]
0x140017046  sub     rsp, 138h
0x14001704d  mov     rax, cs:__security_cookie
0x140017054  xor     rax, rsp
0x140017057  mov     [rbp+70h+var_50], rax
0x14001705b  xorps   xmm0, xmm0
0x14001705e  xor     esi, esi
0x140017060  mov     dil, cl
0x140017063  mov     [rsp+170h+var_140], rsi
0x140017068  xor     edx, edx; Val
0x14001706a  lea     rcx, [rbp+70h+var_B0]; void *
0x14001706e  movups  [rsp+170h+var_138], xmm0
0x140017073  lea     r12d, [rsi+58h]
0x140017077  mov     r8d, r12d; Size
0x14001707a  movups  [rsp+170h+var_128], xmm0
0x14001707f  movups  [rsp+170h+var_118], xmm0
0x140017084  call    memset
0x140017089  lea     r13d, [rsi+48h]
0x14001708d  xor     edx, edx; Val
0x14001708f  mov     r8d, r13d; Size
0x140017092  lea     rcx, [rsp+170h+subLayer]; void *
0x140017097  call    memset
0x14001709c  mov     r14b, 2
0x14001709f  lea     ebx, [rsi+0Ah]
0x1400170a2  test    byte ptr cs:xmmword_1400272E0, r14b
0x1400170a9  lea     r15, WPP_b58024cfe01b3143f1c8b927d5346b48_Traceguids
0x1400170b0  jz      short loc_1400170BF
0x1400170b2  mov     edx, ebx
0x1400170b4  mov     r9b, dil
0x1400170b7  mov     r8, r15
0x1400170ba  call    WPP_SF_c
0x1400170bf  call    cs:__imp_FwpmBfeStateGet0
0x1400170c6  nop     dword ptr [rax+rax+00h]
0x1400170cb  cmp     eax, 3
0x1400170ce  jz      short loc_1400170F5
0x1400170d0  test    byte ptr cs:xmmword_1400272D0, r14b
0x1400170d7  jz      short loc_1400170EB
0x1400170d9  mov     edx, 0Bh
0x1400170de  mov     ecx, 201h
0x1400170e3  mov     r8, r15
0x1400170e6  call    WPP_SF_
0x1400170eb  mov     ebx, 0C00000A3h
0x1400170f0  jmp     loc_14001776E
0x1400170f5  lea     rax, [rsp+170h+var_140]
0x1400170fa  xor     r9d, r9d; session
0x1400170fd  xor     r8d, r8d; authIdentity
0x140017100  mov     [rsp+170h+engineHandle], rax; engineHandle
0x140017105  mov     edx, ebx; authnService
0x140017107  xor     ecx, ecx; serverName
0x140017109  call    cs:__imp_FwpmEngineOpen0
0x140017110  nop     dword ptr [rax+rax+00h]
0x140017115  mov     ebx, eax
0x140017117  test    eax, eax
0x140017119  jns     short loc_140017142
0x14001711b  test    byte ptr cs:xmmword_1400272D0, r14b
0x140017122  jz      loc_14001776E
0x140017128  mov     edx, 0Ch
0x14001712d  mov     ecx, 201h
0x140017132  mov     r9d, eax
0x140017135  mov     r8, r15
0x140017138  call    WPP_SF_d
0x14001713d  jmp     loc_14001776E
0x140017142  mov     rcx, [rsp+170h+var_140]
0x140017147  test    dil, dil
0x14001714a  jz      loc_14001768A
0x140017150  movups  xmm0, cs:IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT
0x140017157  lea     rax, IPxlatOutboundIPv4Callout
0x14001715e  mov     qword ptr [rsp+170h+var_118+8], rsi
0x140017163  mov     qword ptr [rsp+170h+var_128+8], rax
0x140017168  lea     r8, [rbp+70h+var_B0]
0x14001716c  lea     rax, IPxlatNotifyCallout
0x140017173  mov     [rsp+170h+engineHandle], rsi
0x140017178  mov     qword ptr [rsp+170h+var_118], rax
0x14001717d  lea     rdx, [rsp+170h+var_138]
0x140017182  lea     rax, aIpxlatOutbound_0; "IPxlat Outbound IPv4 filter"
0x140017189  xor     r9d, r9d
0x14001718c  movdqu  [rsp+170h+var_138], xmm0
0x140017192  mov     [rbp+70h+var_A0], rax
0x140017196  lea     rax, aFiltersOutgoin_0; "Filters outgoing IPv4 packets into synt"...
0x14001719d  movdqu  [rbp+70h+var_B0], xmm0
0x1400171a2  mov     [rbp+70h+var_98], rax
0x1400171a6  movups  xmm0, xmmword ptr cs:FWPM_LAYER_OUTBOUND_IPPACKET_V4.Data1
0x1400171ad  movdqu  [rbp+70h+var_70], xmm0
0x1400171b2  call    cs:__imp_FwpiCalloutRegisterAndAddWithoutDevice0
0x1400171b9  nop     dword ptr [rax+rax+00h]
0x1400171be  mov     ebx, eax
0x1400171c0  test    eax, eax
0x1400171c2  jns     short loc_1400171FF
0x1400171c4  test    byte ptr cs:xmmword_1400272D0, r14b
0x1400171cb  jz      short loc_1400171E2
0x1400171cd  mov     edx, 0Dh
0x1400171d2  mov     ecx, 201h
0x1400171d7  mov     r9d, eax
0x1400171da  mov     r8, r15
0x1400171dd  call    WPP_SF_d
0x1400171e2  lea     rdx, IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT
0x1400171e9  mov     rcx, [rsp+170h+var_140]
0x1400171ee  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x1400171f5  nop     dword ptr [rax+rax+00h]
0x1400171fa  jmp     loc_14001775D
0x1400171ff  movups  xmm0, xmmword ptr cs:IPXLAT_WFP_OUTBOUND_IPV4_SUBLAYER.Data1
0x140017206  mov     rcx, [rsp+170h+var_140]; engineHandle
0x14001720b  lea     rax, aIpxlatOutbound_2; "IPxlat Outbound IPv4 sub layer"
0x140017212  mov     [rbp+70h+subLayer.displayData.name], rax
0x140017216  lea     rdx, [rsp+170h+subLayer]; subLayer
0x14001721b  lea     rax, aSubLayerForFil_1; "Sub layer for filtering outgoing IPv4 p"...
0x140017222  mov     [rbp+70h+subLayer.flags], esi
0x140017225  mov     edi, 7FFFh
0x14001722a  mov     [rbp+70h+subLayer.displayData.description], rax
0x14001722e  xor     r8d, r8d; sd
0x140017231  mov     [rbp+70h+subLayer.weight], di
0x140017235  movdqu  xmmword ptr [rsp+170h+subLayer.subLayerKey.Data1], xmm0
0x14001723b  call    cs:__imp_FwpmSubLayerAdd0
0x140017242  nop     dword ptr [rax+rax+00h]
0x140017247  mov     ebx, eax
0x140017249  test    eax, eax
0x14001724b  jns     short loc_140017260
0x14001724d  test    byte ptr cs:xmmword_1400272D0, r14b
0x140017254  jz      short loc_1400171E2
0x140017256  mov     edx, 0Eh
0x14001725b  jmp     loc_1400171D2
0x140017260  mov     r8, r12; Size
0x140017263  mov     qword ptr [rsp+170h+var_128], rsi
0x140017268  xor     edx, edx; Val
0x14001726a  lea     rcx, [rbp+70h+var_B0]; void *
0x14001726e  call    memset
0x140017273  mov     r8, r13; Size
0x140017276  lea     rcx, [rsp+170h+subLayer]; void *
0x14001727b  xor     edx, edx; Val
0x14001727d  call    memset
0x140017282  movups  xmm0, cs:IPXLAT_WFP_INBOUND_IPV6_LAYER_CALLOUT
0x140017289  mov     rcx, [rsp+170h+var_140]
0x14001728e  lea     rax, IPxlatInboundIPv6Callout
0x140017295  mov     qword ptr [rsp+170h+var_128+8], rax
0x14001729a  lea     r8, [rbp+70h+var_B0]
0x14001729e  lea     rax, IPxlatNotifyCallout
0x1400172a5  mov     qword ptr [rsp+170h+var_118+8], rsi
0x1400172aa  mov     qword ptr [rsp+170h+var_118], rax
0x1400172af  lea     rdx, [rsp+170h+var_138]
0x1400172b4  lea     rax, aIpxlatInboundI; "IPxlat Inbound IPv6 filter"
0x1400172bb  mov     [rsp+170h+engineHandle], rsi
0x1400172c0  movdqu  [rsp+170h+var_138], xmm0
0x1400172c6  mov     [rbp+70h+var_A0], rax
0x1400172ca  lea     rax, aFiltersIncomin; "Filters incoming IPv6 packets into synt"...
0x1400172d1  movdqu  [rbp+70h+var_B0], xmm0
0x1400172d6  xor     r9d, r9d
0x1400172d9  mov     [rbp+70h+var_98], rax
0x1400172dd  movups  xmm0, xmmword ptr cs:FWPM_LAYER_INBOUND_IPPACKET_V6.Data1
0x1400172e4  movdqu  [rbp+70h+var_70], xmm0
0x1400172e9  call    cs:__imp_FwpiCalloutRegisterAndAddWithoutDevice0
0x1400172f0  nop     dword ptr [rax+rax+00h]
0x1400172f5  mov     ebx, eax
0x1400172f7  test    eax, eax
0x1400172f9  jns     short loc_140017355
0x1400172fb  test    byte ptr cs:xmmword_1400272D0, r14b
0x140017302  jz      short loc_140017319
0x140017304  mov     edx, 0Fh
0x140017309  mov     ecx, 201h
0x14001730e  mov     r9d, eax
0x140017311  mov     r8, r15
0x140017314  call    WPP_SF_d
0x140017319  mov     rcx, [rsp+170h+var_140]
0x14001731e  lea     rdx, IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT
0x140017325  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x14001732c  nop     dword ptr [rax+rax+00h]
0x140017331  mov     rcx, [rsp+170h+var_140]; engineHandle
0x140017336  lea     rdx, IPXLAT_WFP_OUTBOUND_IPV4_SUBLAYER; key
0x14001733d  call    cs:__imp_FwpmSubLayerDeleteByKey0
0x140017344  nop     dword ptr [rax+rax+00h]
0x140017349  lea     rdx, IPXLAT_WFP_INBOUND_IPV6_LAYER_CALLOUT
0x140017350  jmp     loc_1400171E9
0x140017355  movups  xmm0, xmmword ptr cs:IPXLAT_WFP_INBOUND_IPV6_SUBLAYER.Data1
0x14001735c  mov     rcx, [rsp+170h+var_140]; engineHandle
0x140017361  lea     rax, aIpxlatInboundI_0; "IPxlat Inbound IPv6 sub layer"
0x140017368  mov     [rbp+70h+subLayer.displayData.name], rax
0x14001736c  lea     rdx, [rsp+170h+subLayer]; subLayer
0x140017371  lea     rax, aSubLayerForFil_2; "Sub layer for filtering incoming IPv6 p"...
0x140017378  mov     [rbp+70h+subLayer.flags], esi
0x14001737b  xor     r8d, r8d; sd
0x14001737e  mov     [rbp+70h+subLayer.displayData.description], rax
0x140017382  movdqu  xmmword ptr [rsp+170h+subLayer.subLayerKey.Data1], xmm0
0x140017388  mov     [rbp+70h+subLayer.weight], di
0x14001738c  call    cs:__imp_FwpmSubLayerAdd0
0x140017393  nop     dword ptr [rax+rax+00h]
0x140017398  mov     ebx, eax
0x14001739a  test    eax, eax
0x14001739c  jns     short loc_1400173B5
0x14001739e  test    byte ptr cs:xmmword_1400272D0, r14b
0x1400173a5  jz      loc_140017319
0x1400173ab  mov     edx, 10h
0x1400173b0  jmp     loc_140017309
0x1400173b5  mov     r8, r12; Size
0x1400173b8  mov     qword ptr [rsp+170h+var_128], rsi
0x1400173bd  xor     edx, edx; Val
0x1400173bf  lea     rcx, [rbp+70h+var_B0]; void *
0x1400173c3  call    memset
0x1400173c8  mov     r8, r13; Size
0x1400173cb  lea     rcx, [rsp+170h+subLayer]; void *
0x1400173d0  xor     edx, edx; Val
0x1400173d2  call    memset
0x1400173d7  movups  xmm0, cs:IPXLAT_WFP_FORWARD_IPV4_LAYER_CALLOUT
0x1400173de  mov     rcx, [rsp+170h+var_140]
0x1400173e3  lea     rax, IPxlatForwardIPv4Callout
0x1400173ea  mov     qword ptr [rsp+170h+var_128+8], rax
0x1400173ef  lea     r8, [rbp+70h+var_B0]
0x1400173f3  lea     rax, IPxlatNotifyCallout
0x1400173fa  mov     qword ptr [rsp+170h+var_118+8], rsi
0x1400173ff  mov     qword ptr [rsp+170h+var_118], rax
0x140017404  lea     rdx, [rsp+170h+var_138]
0x140017409  lea     rax, aIpxlatForwardI; "IPxlat Forward IPv4 filter"
0x140017410  mov     [rsp+170h+engineHandle], rsi
0x140017415  movdqu  [rsp+170h+var_138], xmm0
0x14001741b  mov     [rbp+70h+var_A0], rax
0x14001741f  lea     rax, aFiltersForward; "Filters forwarded IPv4 packets into syn"...
0x140017426  movdqu  [rbp+70h+var_B0], xmm0
0x14001742b  xor     r9d, r9d
0x14001742e  mov     [rbp+70h+var_98], rax
0x140017432  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPFORWARD_V4.Data1
0x140017439  movdqu  [rbp+70h+var_70], xmm0
0x14001743e  call    cs:__imp_FwpiCalloutRegisterAndAddWithoutDevice0
0x140017445  nop     dword ptr [rax+rax+00h]
0x14001744a  mov     ebx, eax
0x14001744c  test    eax, eax
0x14001744e  jns     loc_1400174DE
0x140017454  test    byte ptr cs:xmmword_1400272D0, r14b
0x14001745b  jz      short loc_140017472
0x14001745d  mov     edx, 11h
0x140017462  mov     ecx, 201h
0x140017467  mov     r9d, eax
0x14001746a  mov     r8, r15
0x14001746d  call    WPP_SF_d
0x140017472  mov     rcx, [rsp+170h+var_140]
0x140017477  lea     rdx, IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT
0x14001747e  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x140017485  nop     dword ptr [rax+rax+00h]
0x14001748a  mov     rcx, [rsp+170h+var_140]; engineHandle
0x14001748f  lea     rdx, IPXLAT_WFP_OUTBOUND_IPV4_SUBLAYER; key
0x140017496  call    cs:__imp_FwpmSubLayerDeleteByKey0
0x14001749d  nop     dword ptr [rax+rax+00h]
0x1400174a2  mov     rcx, [rsp+170h+var_140]
0x1400174a7  lea     rdx, IPXLAT_WFP_INBOUND_IPV6_LAYER_CALLOUT
0x1400174ae  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x1400174b5  nop     dword ptr [rax+rax+00h]
0x1400174ba  mov     rcx, [rsp+170h+var_140]; engineHandle
0x1400174bf  lea     rdx, IPXLAT_WFP_INBOUND_IPV6_SUBLAYER; key
0x1400174c6  call    cs:__imp_FwpmSubLayerDeleteByKey0
0x1400174cd  nop     dword ptr [rax+rax+00h]
0x1400174d2  lea     rdx, IPXLAT_WFP_FORWARD_IPV4_LAYER_CALLOUT
0x1400174d9  jmp     loc_1400171E9
0x1400174de  movups  xmm0, xmmword ptr cs:IPXLAT_WFP_FORWARD_IPV4_SUBLAYER.Data1
0x1400174e5  mov     rcx, [rsp+170h+var_140]; engineHandle
0x1400174ea  lea     rax, aIpxlatForwardI_0; "IPxlat Forward IPv4 sub layer"
0x1400174f1  mov     [rbp+70h+subLayer.displayData.name], rax
0x1400174f5  lea     rdx, [rsp+170h+subLayer]; subLayer
0x1400174fa  lea     rax, aSubLayerForFil_0; "Sub layer for filtering forwarded IPv4 "...
0x140017501  mov     [rbp+70h+subLayer.flags], esi
0x140017504  xor     r8d, r8d; sd
0x140017507  mov     [rbp+70h+subLayer.displayData.description], rax
0x14001750b  movdqu  xmmword ptr [rsp+170h+subLayer.subLayerKey.Data1], xmm0
0x140017511  mov     [rbp+70h+subLayer.weight], di
0x140017515  call    cs:__imp_FwpmSubLayerAdd0
0x14001751c  nop     dword ptr [rax+rax+00h]
0x140017521  mov     ebx, eax
0x140017523  test    eax, eax
0x140017525  jns     short loc_14001753E
0x140017527  test    byte ptr cs:xmmword_1400272D0, r14b
0x14001752e  jz      loc_140017472
0x140017534  mov     edx, 12h
0x140017539  jmp     loc_140017462
0x14001753e  mov     eax, cs:Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_featureState
0x140017544  test    al, 10h
0x140017546  jz      short loc_14001754D
0x140017548  and     eax, 1
0x14001754b  jmp     short loc_140017552
0x14001754d  call    Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_IsEnabledDeviceUsageNoInline
0x140017552  test    eax, eax
0x140017554  jz      loc_14001775D
0x14001755a  movups  xmm0, cs:IPXLAT_WFP_OUTBOUND_ETHERNET_LAYER_CALLOUT
0x140017561  mov     rcx, [rsp+170h+var_140]
0x140017566  lea     rax, IPxlatOutboundEthernetCallout
0x14001756d  mov     qword ptr [rsp+170h+var_128+8], rax
0x140017572  lea     r8, [rbp+70h+var_B0]
0x140017576  lea     rax, IPxlatNotifyCallout
0x14001757d  mov     qword ptr [rsp+170h+var_118+8], rsi
0x140017582  mov     qword ptr [rsp+170h+var_118], rax
0x140017587  lea     rdx, [rsp+170h+var_138]
0x14001758c  lea     rax, aIpxlatOutbound_1; "IPxlat Outbound Ethernet filter"
0x140017593  mov     [rsp+170h+engineHandle], rsi
0x140017598  movdqu  [rsp+170h+var_138], xmm0
0x14001759e  mov     [rbp+70h+var_A0], rax
0x1400175a2  lea     rax, aFiltersOutgoin; "Filters outgoing ethernet packets to bl"...
0x1400175a9  movdqu  [rbp+70h+var_B0], xmm0
  ... truncated ...
```
