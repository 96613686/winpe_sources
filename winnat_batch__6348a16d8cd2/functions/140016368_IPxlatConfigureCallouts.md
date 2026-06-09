# IPxlatConfigureCallouts

- ea: `0x140016368`
- end: `0x140016ae3`
- name: `IPxlatConfigureCallouts`
- size: `1915`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140015940`
- `0x1400159b4`
- `0x140035cac`

## callees

- `0x140016310`
- `0x140016368`
- `0x14001ede0`
- `0x14001f440`
- `0x14002d008`
- `0x14002d040`
- `0x14002d4b0`

## import_xrefs

- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140016522`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140016659`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400167b2`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400167e2`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400169c5`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400169f5`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140016a25`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140016a6d`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140016522`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140016659`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400167b2`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400167e2`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400169c5`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400169f5`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140016a25`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140016a6d`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x1400164e6`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x14001661d`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x140016772`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x1400168f5`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x1400164e6`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x14001661d`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x140016772`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x1400168f5`
- `fwpkclnt!FwpmBfeStateGet0` at `0x1400163f3`
- `fwpkclnt!FwpmBfeStateGet0` at `0x1400163f3`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x140016671`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x1400167ca`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x1400167fa`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x1400169dd`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x140016a0d`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x140016a3d`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x140016a85`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x140016671`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x1400167ca`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x1400167fa`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x1400169dd`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x140016a0d`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x140016a3d`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x140016a85`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x14001656f`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x1400166c0`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x140016849`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x140016968`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x14001656f`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x1400166c0`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x140016849`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x140016968`
- `fwpkclnt!FwpmEngineClose0` at `0x140016a96`
- `fwpkclnt!FwpmEngineClose0` at `0x140016a96`
- `fwpkclnt!FwpmEngineOpen0` at `0x14001643d`
- `fwpkclnt!FwpmEngineOpen0` at `0x14001643d`

## string_xrefs

- `0x1400165fe`: `Filters incoming IPv6 packets into synthetic IPv4 packets`
- `0x1400166a5`: `Sub layer for filtering incoming IPv6 packets into synthetic IPv4 packets`

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
  if ( (xmmword_1400262E0 & 2) != 0 )
  {
    LOBYTE(v3) = a1;
    WPP_SF_c(v2, 10, WPP_639724ddcd2939a457521487d2ab8eb6_Traceguids, v3);
  }
  if ( FwpmBfeStateGet0() != FWPM_SERVICE_RUNNING )
  {
    if ( (xmmword_1400262D0 & 2) != 0 )
      WPP_SF_(513, 11, WPP_639724ddcd2939a457521487d2ab8eb6_Traceguids);
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
      if ( (xmmword_1400262D0 & 2) == 0 )
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
      WPP_SF_d(513, v7, WPP_639724ddcd2939a457521487d2ab8eb6_Traceguids, (unsigned int)v6);
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
      if ( (xmmword_1400262D0 & 2) == 0 )
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
      if ( (xmmword_1400262D0 & 2) == 0 )
      {
LABEL_24:
        FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT);
        FwpmSubLayerDeleteByKey0(engineHandle, &IPXLAT_WFP_OUTBOUND_IPV4_SUBLAYER);
        v8 = &IPXLAT_WFP_INBOUND_IPV6_LAYER_CALLOUT;
        goto LABEL_16;
      }
      v10 = 15;
LABEL_23:
      WPP_SF_d(513, v10, WPP_639724ddcd2939a457521487d2ab8eb6_Traceguids, (unsigned int)v9);
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
      if ( (xmmword_1400262D0 & 2) == 0 )
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
      if ( (xmmword_1400262D0 & 2) == 0 )
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
      WPP_SF_d(513, v12, WPP_639724ddcd2939a457521487d2ab8eb6_Traceguids, (unsigned int)v11);
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
      if ( (xmmword_1400262D0 & 2) == 0 )
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
      if ( (xmmword_1400262D0 & 2) == 0 )
        goto LABEL_44;
      v15 = 20;
    }
    else
    {
      if ( (xmmword_1400262D0 & 2) == 0 )
      {
LABEL_44:
        v8 = &IPXLAT_WFP_OUTBOUND_ETHERNET_LAYER_CALLOUT;
        goto LABEL_16;
      }
      v15 = 19;
    }
    WPP_SF_d(513, v15, WPP_639724ddcd2939a457521487d2ab8eb6_Traceguids, (unsigned int)v14);
    goto LABEL_44;
  }
  if ( (xmmword_1400262D0 & 2) != 0 )
    WPP_SF_d(513, 12, WPP_639724ddcd2939a457521487d2ab8eb6_Traceguids, (unsigned int)v5);
LABEL_55:
  if ( (xmmword_1400262E0 & 2) != 0 )
    WPP_SF_d(1025, 21, WPP_639724ddcd2939a457521487d2ab8eb6_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x140016368  push    rbp
0x14001636a  push    rbx
0x14001636b  push    rsi
0x14001636c  push    rdi
0x14001636d  push    r12
0x14001636f  push    r13
0x140016371  push    r14
0x140016373  push    r15
0x140016375  lea     rbp, [rsp-38h]
0x14001637a  sub     rsp, 138h
0x140016381  mov     rax, cs:__security_cookie
0x140016388  xor     rax, rsp
0x14001638b  mov     [rbp+70h+var_50], rax
0x14001638f  xorps   xmm0, xmm0
0x140016392  xor     esi, esi
0x140016394  mov     dil, cl
0x140016397  mov     [rsp+170h+var_140], rsi
0x14001639c  xor     edx, edx; Val
0x14001639e  lea     rcx, [rbp+70h+var_B0]; void *
0x1400163a2  movups  [rsp+170h+var_138], xmm0
0x1400163a7  lea     r12d, [rsi+58h]
0x1400163ab  mov     r8d, r12d; Size
0x1400163ae  movups  [rsp+170h+var_128], xmm0
0x1400163b3  movups  [rsp+170h+var_118], xmm0
0x1400163b8  call    memset
0x1400163bd  lea     r13d, [rsi+48h]
0x1400163c1  xor     edx, edx; Val
0x1400163c3  mov     r8d, r13d; Size
0x1400163c6  lea     rcx, [rsp+170h+subLayer]; void *
0x1400163cb  call    memset
0x1400163d0  mov     r14b, 2
0x1400163d3  lea     ebx, [rsi+0Ah]
0x1400163d6  test    byte ptr cs:xmmword_1400262E0, r14b
0x1400163dd  lea     r15, WPP_639724ddcd2939a457521487d2ab8eb6_Traceguids
0x1400163e4  jz      short loc_1400163F3
0x1400163e6  mov     edx, ebx
0x1400163e8  mov     r9b, dil
0x1400163eb  mov     r8, r15
0x1400163ee  call    WPP_SF_c
0x1400163f3  call    cs:__imp_FwpmBfeStateGet0
0x1400163fa  nop     dword ptr [rax+rax+00h]
0x1400163ff  cmp     eax, 3
0x140016402  jz      short loc_140016429
0x140016404  test    byte ptr cs:xmmword_1400262D0, r14b
0x14001640b  jz      short loc_14001641F
0x14001640d  mov     edx, 0Bh
0x140016412  mov     ecx, 201h
0x140016417  mov     r8, r15
0x14001641a  call    WPP_SF_
0x14001641f  mov     ebx, 0C00000A3h
0x140016424  jmp     loc_140016AA2
0x140016429  lea     rax, [rsp+170h+var_140]
0x14001642e  xor     r9d, r9d; session
0x140016431  xor     r8d, r8d; authIdentity
0x140016434  mov     [rsp+170h+engineHandle], rax; engineHandle
0x140016439  mov     edx, ebx; authnService
0x14001643b  xor     ecx, ecx; serverName
0x14001643d  call    cs:__imp_FwpmEngineOpen0
0x140016444  nop     dword ptr [rax+rax+00h]
0x140016449  mov     ebx, eax
0x14001644b  test    eax, eax
0x14001644d  jns     short loc_140016476
0x14001644f  test    byte ptr cs:xmmword_1400262D0, r14b
0x140016456  jz      loc_140016AA2
0x14001645c  mov     edx, 0Ch
0x140016461  mov     ecx, 201h
0x140016466  mov     r9d, eax
0x140016469  mov     r8, r15
0x14001646c  call    WPP_SF_d
0x140016471  jmp     loc_140016AA2
0x140016476  mov     rcx, [rsp+170h+var_140]
0x14001647b  test    dil, dil
0x14001647e  jz      loc_1400169BE
0x140016484  movups  xmm0, cs:IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT
0x14001648b  lea     rax, IPxlatOutboundIPv4Callout
0x140016492  mov     qword ptr [rsp+170h+var_118+8], rsi
0x140016497  mov     qword ptr [rsp+170h+var_128+8], rax
0x14001649c  lea     r8, [rbp+70h+var_B0]
0x1400164a0  lea     rax, IPxlatNotifyCallout
0x1400164a7  mov     [rsp+170h+engineHandle], rsi
0x1400164ac  mov     qword ptr [rsp+170h+var_118], rax
0x1400164b1  lea     rdx, [rsp+170h+var_138]
0x1400164b6  lea     rax, aIpxlatOutbound_0; "IPxlat Outbound IPv4 filter"
0x1400164bd  xor     r9d, r9d
0x1400164c0  movdqu  [rsp+170h+var_138], xmm0
0x1400164c6  mov     [rbp+70h+var_A0], rax
0x1400164ca  lea     rax, aFiltersOutgoin_0; "Filters outgoing IPv4 packets into synt"...
0x1400164d1  movdqu  [rbp+70h+var_B0], xmm0
0x1400164d6  mov     [rbp+70h+var_98], rax
0x1400164da  movups  xmm0, xmmword ptr cs:FWPM_LAYER_OUTBOUND_IPPACKET_V4.Data1
0x1400164e1  movdqu  [rbp+70h+var_70], xmm0
0x1400164e6  call    cs:__imp_FwpiCalloutRegisterAndAddWithoutDevice0
0x1400164ed  nop     dword ptr [rax+rax+00h]
0x1400164f2  mov     ebx, eax
0x1400164f4  test    eax, eax
0x1400164f6  jns     short loc_140016533
0x1400164f8  test    byte ptr cs:xmmword_1400262D0, r14b
0x1400164ff  jz      short loc_140016516
0x140016501  mov     edx, 0Dh
0x140016506  mov     ecx, 201h
0x14001650b  mov     r9d, eax
0x14001650e  mov     r8, r15
0x140016511  call    WPP_SF_d
0x140016516  lea     rdx, IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT
0x14001651d  mov     rcx, [rsp+170h+var_140]
0x140016522  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x140016529  nop     dword ptr [rax+rax+00h]
0x14001652e  jmp     loc_140016A91
0x140016533  movups  xmm0, xmmword ptr cs:IPXLAT_WFP_OUTBOUND_IPV4_SUBLAYER.Data1
0x14001653a  mov     rcx, [rsp+170h+var_140]; engineHandle
0x14001653f  lea     rax, aIpxlatOutbound_2; "IPxlat Outbound IPv4 sub layer"
0x140016546  mov     [rbp+70h+subLayer.displayData.name], rax
0x14001654a  lea     rdx, [rsp+170h+subLayer]; subLayer
0x14001654f  lea     rax, aSubLayerForFil_1; "Sub layer for filtering outgoing IPv4 p"...
0x140016556  mov     [rbp+70h+subLayer.flags], esi
0x140016559  mov     edi, 7FFFh
0x14001655e  mov     [rbp+70h+subLayer.displayData.description], rax
0x140016562  xor     r8d, r8d; sd
0x140016565  mov     [rbp+70h+subLayer.weight], di
0x140016569  movdqu  xmmword ptr [rsp+170h+subLayer.subLayerKey.Data1], xmm0
0x14001656f  call    cs:__imp_FwpmSubLayerAdd0
0x140016576  nop     dword ptr [rax+rax+00h]
0x14001657b  mov     ebx, eax
0x14001657d  test    eax, eax
0x14001657f  jns     short loc_140016594
0x140016581  test    byte ptr cs:xmmword_1400262D0, r14b
0x140016588  jz      short loc_140016516
0x14001658a  mov     edx, 0Eh
0x14001658f  jmp     loc_140016506
0x140016594  mov     r8, r12; Size
0x140016597  mov     qword ptr [rsp+170h+var_128], rsi
0x14001659c  xor     edx, edx; Val
0x14001659e  lea     rcx, [rbp+70h+var_B0]; void *
0x1400165a2  call    memset
0x1400165a7  mov     r8, r13; Size
0x1400165aa  lea     rcx, [rsp+170h+subLayer]; void *
0x1400165af  xor     edx, edx; Val
0x1400165b1  call    memset
0x1400165b6  movups  xmm0, cs:IPXLAT_WFP_INBOUND_IPV6_LAYER_CALLOUT
0x1400165bd  mov     rcx, [rsp+170h+var_140]
0x1400165c2  lea     rax, IPxlatInboundIPv6Callout
0x1400165c9  mov     qword ptr [rsp+170h+var_128+8], rax
0x1400165ce  lea     r8, [rbp+70h+var_B0]
0x1400165d2  lea     rax, IPxlatNotifyCallout
0x1400165d9  mov     qword ptr [rsp+170h+var_118+8], rsi
0x1400165de  mov     qword ptr [rsp+170h+var_118], rax
0x1400165e3  lea     rdx, [rsp+170h+var_138]
0x1400165e8  lea     rax, aIpxlatInboundI; "IPxlat Inbound IPv6 filter"
0x1400165ef  mov     [rsp+170h+engineHandle], rsi
0x1400165f4  movdqu  [rsp+170h+var_138], xmm0
0x1400165fa  mov     [rbp+70h+var_A0], rax
0x1400165fe  lea     rax, aFiltersIncomin; "Filters incoming IPv6 packets into synt"...
0x140016605  movdqu  [rbp+70h+var_B0], xmm0
0x14001660a  xor     r9d, r9d
0x14001660d  mov     [rbp+70h+var_98], rax
0x140016611  movups  xmm0, xmmword ptr cs:FWPM_LAYER_INBOUND_IPPACKET_V6.Data1
0x140016618  movdqu  [rbp+70h+var_70], xmm0
0x14001661d  call    cs:__imp_FwpiCalloutRegisterAndAddWithoutDevice0
0x140016624  nop     dword ptr [rax+rax+00h]
0x140016629  mov     ebx, eax
0x14001662b  test    eax, eax
0x14001662d  jns     short loc_140016689
0x14001662f  test    byte ptr cs:xmmword_1400262D0, r14b
0x140016636  jz      short loc_14001664D
0x140016638  mov     edx, 0Fh
0x14001663d  mov     ecx, 201h
0x140016642  mov     r9d, eax
0x140016645  mov     r8, r15
0x140016648  call    WPP_SF_d
0x14001664d  mov     rcx, [rsp+170h+var_140]
0x140016652  lea     rdx, IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT
0x140016659  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x140016660  nop     dword ptr [rax+rax+00h]
0x140016665  mov     rcx, [rsp+170h+var_140]; engineHandle
0x14001666a  lea     rdx, IPXLAT_WFP_OUTBOUND_IPV4_SUBLAYER; key
0x140016671  call    cs:__imp_FwpmSubLayerDeleteByKey0
0x140016678  nop     dword ptr [rax+rax+00h]
0x14001667d  lea     rdx, IPXLAT_WFP_INBOUND_IPV6_LAYER_CALLOUT
0x140016684  jmp     loc_14001651D
0x140016689  movups  xmm0, xmmword ptr cs:IPXLAT_WFP_INBOUND_IPV6_SUBLAYER.Data1
0x140016690  mov     rcx, [rsp+170h+var_140]; engineHandle
0x140016695  lea     rax, aIpxlatInboundI_0; "IPxlat Inbound IPv6 sub layer"
0x14001669c  mov     [rbp+70h+subLayer.displayData.name], rax
0x1400166a0  lea     rdx, [rsp+170h+subLayer]; subLayer
0x1400166a5  lea     rax, aSubLayerForFil_2; "Sub layer for filtering incoming IPv6 p"...
0x1400166ac  mov     [rbp+70h+subLayer.flags], esi
0x1400166af  xor     r8d, r8d; sd
0x1400166b2  mov     [rbp+70h+subLayer.displayData.description], rax
0x1400166b6  movdqu  xmmword ptr [rsp+170h+subLayer.subLayerKey.Data1], xmm0
0x1400166bc  mov     [rbp+70h+subLayer.weight], di
0x1400166c0  call    cs:__imp_FwpmSubLayerAdd0
0x1400166c7  nop     dword ptr [rax+rax+00h]
0x1400166cc  mov     ebx, eax
0x1400166ce  test    eax, eax
0x1400166d0  jns     short loc_1400166E9
0x1400166d2  test    byte ptr cs:xmmword_1400262D0, r14b
0x1400166d9  jz      loc_14001664D
0x1400166df  mov     edx, 10h
0x1400166e4  jmp     loc_14001663D
0x1400166e9  mov     r8, r12; Size
0x1400166ec  mov     qword ptr [rsp+170h+var_128], rsi
0x1400166f1  xor     edx, edx; Val
0x1400166f3  lea     rcx, [rbp+70h+var_B0]; void *
0x1400166f7  call    memset
0x1400166fc  mov     r8, r13; Size
0x1400166ff  lea     rcx, [rsp+170h+subLayer]; void *
0x140016704  xor     edx, edx; Val
0x140016706  call    memset
0x14001670b  movups  xmm0, cs:IPXLAT_WFP_FORWARD_IPV4_LAYER_CALLOUT
0x140016712  mov     rcx, [rsp+170h+var_140]
0x140016717  lea     rax, IPxlatForwardIPv4Callout
0x14001671e  mov     qword ptr [rsp+170h+var_128+8], rax
0x140016723  lea     r8, [rbp+70h+var_B0]
0x140016727  lea     rax, IPxlatNotifyCallout
0x14001672e  mov     qword ptr [rsp+170h+var_118+8], rsi
0x140016733  mov     qword ptr [rsp+170h+var_118], rax
0x140016738  lea     rdx, [rsp+170h+var_138]
0x14001673d  lea     rax, aIpxlatForwardI; "IPxlat Forward IPv4 filter"
0x140016744  mov     [rsp+170h+engineHandle], rsi
0x140016749  movdqu  [rsp+170h+var_138], xmm0
0x14001674f  mov     [rbp+70h+var_A0], rax
0x140016753  lea     rax, aFiltersForward; "Filters forwarded IPv4 packets into syn"...
0x14001675a  movdqu  [rbp+70h+var_B0], xmm0
0x14001675f  xor     r9d, r9d
0x140016762  mov     [rbp+70h+var_98], rax
0x140016766  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPFORWARD_V4.Data1
0x14001676d  movdqu  [rbp+70h+var_70], xmm0
0x140016772  call    cs:__imp_FwpiCalloutRegisterAndAddWithoutDevice0
0x140016779  nop     dword ptr [rax+rax+00h]
0x14001677e  mov     ebx, eax
0x140016780  test    eax, eax
0x140016782  jns     loc_140016812
0x140016788  test    byte ptr cs:xmmword_1400262D0, r14b
0x14001678f  jz      short loc_1400167A6
0x140016791  mov     edx, 11h
0x140016796  mov     ecx, 201h
0x14001679b  mov     r9d, eax
0x14001679e  mov     r8, r15
0x1400167a1  call    WPP_SF_d
0x1400167a6  mov     rcx, [rsp+170h+var_140]
0x1400167ab  lea     rdx, IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT
0x1400167b2  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x1400167b9  nop     dword ptr [rax+rax+00h]
0x1400167be  mov     rcx, [rsp+170h+var_140]; engineHandle
0x1400167c3  lea     rdx, IPXLAT_WFP_OUTBOUND_IPV4_SUBLAYER; key
0x1400167ca  call    cs:__imp_FwpmSubLayerDeleteByKey0
0x1400167d1  nop     dword ptr [rax+rax+00h]
0x1400167d6  mov     rcx, [rsp+170h+var_140]
0x1400167db  lea     rdx, IPXLAT_WFP_INBOUND_IPV6_LAYER_CALLOUT
0x1400167e2  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x1400167e9  nop     dword ptr [rax+rax+00h]
0x1400167ee  mov     rcx, [rsp+170h+var_140]; engineHandle
0x1400167f3  lea     rdx, IPXLAT_WFP_INBOUND_IPV6_SUBLAYER; key
0x1400167fa  call    cs:__imp_FwpmSubLayerDeleteByKey0
0x140016801  nop     dword ptr [rax+rax+00h]
0x140016806  lea     rdx, IPXLAT_WFP_FORWARD_IPV4_LAYER_CALLOUT
0x14001680d  jmp     loc_14001651D
0x140016812  movups  xmm0, xmmword ptr cs:IPXLAT_WFP_FORWARD_IPV4_SUBLAYER.Data1
0x140016819  mov     rcx, [rsp+170h+var_140]; engineHandle
0x14001681e  lea     rax, aIpxlatForwardI_0; "IPxlat Forward IPv4 sub layer"
0x140016825  mov     [rbp+70h+subLayer.displayData.name], rax
0x140016829  lea     rdx, [rsp+170h+subLayer]; subLayer
0x14001682e  lea     rax, aSubLayerForFil_0; "Sub layer for filtering forwarded IPv4 "...
0x140016835  mov     [rbp+70h+subLayer.flags], esi
0x140016838  xor     r8d, r8d; sd
0x14001683b  mov     [rbp+70h+subLayer.displayData.description], rax
0x14001683f  movdqu  xmmword ptr [rsp+170h+subLayer.subLayerKey.Data1], xmm0
0x140016845  mov     [rbp+70h+subLayer.weight], di
0x140016849  call    cs:__imp_FwpmSubLayerAdd0
0x140016850  nop     dword ptr [rax+rax+00h]
0x140016855  mov     ebx, eax
0x140016857  test    eax, eax
0x140016859  jns     short loc_140016872
0x14001685b  test    byte ptr cs:xmmword_1400262D0, r14b
0x140016862  jz      loc_1400167A6
0x140016868  mov     edx, 12h
0x14001686d  jmp     loc_140016796
0x140016872  mov     eax, cs:Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_featureState
0x140016878  test    al, 10h
0x14001687a  jz      short loc_140016881
0x14001687c  and     eax, 1
0x14001687f  jmp     short loc_140016886
0x140016881  call    Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_IsEnabledDeviceUsageNoInline
0x140016886  test    eax, eax
0x140016888  jz      loc_140016A91
0x14001688e  movups  xmm0, cs:IPXLAT_WFP_OUTBOUND_ETHERNET_LAYER_CALLOUT
0x140016895  mov     rcx, [rsp+170h+var_140]
0x14001689a  lea     rax, IPxlatOutboundEthernetCallout
0x1400168a1  mov     qword ptr [rsp+170h+var_128+8], rax
0x1400168a6  lea     r8, [rbp+70h+var_B0]
0x1400168aa  lea     rax, IPxlatNotifyCallout
0x1400168b1  mov     qword ptr [rsp+170h+var_118+8], rsi
0x1400168b6  mov     qword ptr [rsp+170h+var_118], rax
0x1400168bb  lea     rdx, [rsp+170h+var_138]
0x1400168c0  lea     rax, aIpxlatOutbound_1; "IPxlat Outbound Ethernet filter"
0x1400168c7  mov     [rsp+170h+engineHandle], rsi
0x1400168cc  movdqu  [rsp+170h+var_138], xmm0
0x1400168d2  mov     [rbp+70h+var_A0], rax
0x1400168d6  lea     rax, aFiltersOutgoin; "Filters outgoing ethernet packets to bl"...
0x1400168dd  movdqu  [rbp+70h+var_B0], xmm0
  ... truncated ...
```
