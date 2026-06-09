# IPxlatConfigureFiltersForInstance

- ea: `0x1400177b8`
- end: `0x140017eb8`
- name: `IPxlatConfigureFiltersForInstance`
- size: `1792`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400164a8`
- `0x140016760`
- `0x140016af0`
- `0x1400185a0`

## callees

- `0x14000caa0`
- `0x14000e390`
- `0x140016ea4`
- `0x140016fdc`
- `0x1400177b8`
- `0x14001f320`
- `0x14001f980`
- `0x14002e008`

## import_xrefs

- `fwpkclnt!FwpmTransactionAbort0` at `0x140017d77`
- `fwpkclnt!FwpmTransactionAbort0` at `0x140017d77`
- `fwpkclnt!FwpmTransactionBegin0` at `0x1400178b5`
- `fwpkclnt!FwpmTransactionBegin0` at `0x1400178b5`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x140017dac`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x140017dd5`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x140017dfe`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x140017e3f`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x140017dac`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x140017dd5`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x140017dfe`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x140017e3f`
- `fwpkclnt!FwpmFilterAdd0` at `0x14001799f`
- `fwpkclnt!FwpmFilterAdd0` at `0x140017b04`
- `fwpkclnt!FwpmFilterAdd0` at `0x140017c13`
- `fwpkclnt!FwpmFilterAdd0` at `0x140017d42`
- `fwpkclnt!FwpmFilterAdd0` at `0x14001799f`
- `fwpkclnt!FwpmFilterAdd0` at `0x140017b04`
- `fwpkclnt!FwpmFilterAdd0` at `0x140017c13`
- `fwpkclnt!FwpmFilterAdd0` at `0x140017d42`
- `fwpkclnt!FwpmEngineClose0` at `0x140017e5f`
- `fwpkclnt!FwpmEngineClose0` at `0x140017e5f`
- `fwpkclnt!FwpmEngineOpen0` at `0x140017819`
- `fwpkclnt!FwpmEngineOpen0` at `0x140017819`
- `fwpkclnt!FwpmTransactionCommit0` at `0x140017d8d`
- `fwpkclnt!FwpmTransactionCommit0` at `0x140017d8d`

## pseudocode

```c
__int64 __fastcall IPxlatConfigureFiltersForInstance(__int64 a1, char a2)
{
  NTSTATUS v4; // eax
  NTSTATUS v5; // ebx
  unsigned int v6; // eax
  NTSTATUS v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // eax
  int v14; // eax
  __int128 v15; // xmm0
  __int128 *v16; // rax
  unsigned int v17; // eax
  int v18; // eax
  int v19; // eax
  UINT64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  UINT64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  UINT64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  int IsEnabledDeviceUsageNoInline; // eax
  UINT64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  HANDLE engineHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v39; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v40[16]; // [rsp+40h] [rbp-C0h] BYREF
  FWPM_FILTER0 filter; // [rsp+50h] [rbp-B0h] BYREF
  FWPM_FILTER0 v42; // [rsp+120h] [rbp+20h] BYREF
  FWPM_FILTER0 v43; // [rsp+1F0h] [rbp+F0h] BYREF
  FWPM_FILTER0 v44; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int128 v45; // [rsp+390h] [rbp+290h] BYREF
  _OWORD v46[5]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _OWORD v47[5]; // [rsp+3F0h] [rbp+2F0h] BYREF
  _OWORD v48[5]; // [rsp+440h] [rbp+340h] BYREF
  _OWORD v49[8]; // [rsp+490h] [rbp+390h] BYREF

  engineHandle = 0;
  v45 = 0;
  v4 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( !a2 )
    {
      v20 = *(_QWORD *)(a1 + 48);
      if ( v20 )
      {
        v5 = FwpmFilterDeleteById0(engineHandle, v20);
        if ( v5 < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v22, v21, v23);
        *(_QWORD *)(a1 + 48) = 0;
      }
      v24 = *(_QWORD *)(a1 + 56);
      if ( v24 )
      {
        v5 = FwpmFilterDeleteById0(engineHandle, v24);
        if ( v5 < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v26, v25, v27);
        *(_QWORD *)(a1 + 56) = 0;
      }
      v28 = *(_QWORD *)(a1 + 64);
      if ( v28 )
      {
        v5 = FwpmFilterDeleteById0(engineHandle, v28);
        if ( v5 < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v30, v29, v31);
        *(_QWORD *)(a1 + 64) = 0;
      }
      if ( (Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_featureState & 0x10) != 0 )
        IsEnabledDeviceUsageNoInline = Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_featureState & 1;
      else
        IsEnabledDeviceUsageNoInline = Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_IsEnabledDeviceUsageNoInline();
      if ( IsEnabledDeviceUsageNoInline )
      {
        v33 = *(_QWORD *)(a1 + 72);
        if ( v33 )
        {
          v5 = FwpmFilterDeleteById0(engineHandle, v33);
          if ( v5 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgsKM(v35, v34, v36);
          *(_QWORD *)(a1 + 72) = 0;
        }
      }
      goto LABEL_51;
    }
    memset(&filter, 0, sizeof(filter));
    memset(&v42, 0, sizeof(v42));
    memset(&v43, 0, sizeof(v43));
    memset(&v44, 0, sizeof(v44));
    v39 = -4;
    v5 = FwpmTransactionBegin0(engineHandle, 0);
    if ( v5 < 0 )
    {
LABEL_51:
      FwpmEngineClose0(engineHandle);
      goto LABEL_52;
    }
    filter.displayData.name = L"IPxlatOutboundIPv4filter";
    filter.layerKey = FWPM_LAYER_OUTBOUND_IPPACKET_V4;
    filter.numFilterConditions = 2;
    filter.filterCondition = (FWPM_FILTER_CONDITION0 *)v46;
    filter.action.type = 20483;
    filter.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT;
    filter.weight.type = FWP_UINT64;
    filter.subLayerKey = IPXLAT_WFP_OUTBOUND_IPV4_SUBLAYER;
    filter.weight.uint64 = (UINT64 *)&v39;
    memset(v46, 0, sizeof(v46));
    LODWORD(v46[2]) = *(_DWORD *)(a1 + 24);
    v6 = *(_DWORD *)(a1 + 80);
    v46[0] = FWPM_CONDITION_INTERFACE_INDEX;
    LODWORD(v46[1]) = 0;
    DWORD2(v46[1]) = 3;
    *(GUID *)((char *)&v46[2] + 8) = FWPM_CONDITION_IP_LOCAL_ADDRESS;
    DWORD2(v46[3]) = 0;
    LODWORD(v46[4]) = 3;
    DWORD2(v46[4]) = _byteswap_ulong(v6);
    v7 = FwpmFilterAdd0(engineHandle, &filter, 0, (UINT64 *)(a1 + 48));
    v5 = v7;
    if ( v7 >= 0 )
    {
      v42.displayData.name = L"IPxlatInboundIPv6filter";
      v42.layerKey = FWPM_LAYER_INBOUND_IPPACKET_V6;
      v42.numFilterConditions = 3;
      v42.filterCondition = (FWPM_FILTER_CONDITION0 *)v49;
      v42.action.type = 20483;
      v42.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)IPXLAT_WFP_INBOUND_IPV6_LAYER_CALLOUT;
      v42.weight.type = FWP_UINT64;
      v42.subLayerKey = IPXLAT_WFP_INBOUND_IPV6_SUBLAYER;
      v42.weight.uint64 = (UINT64 *)&v39;
      memset(v49, 0, 0x78u);
      v13 = *(_DWORD *)(a1 + 24);
      LODWORD(v49[1]) = 0;
      v49[0] = FWPM_CONDITION_INTERFACE_INDEX;
      DWORD2(v49[1]) = 3;
      LODWORD(v49[2]) = v13;
      DWORD2(v49[3]) = 0;
      *(GUID *)((char *)&v49[2] + 8) = FWPM_CONDITION_IP_LOCAL_ADDRESS;
      LODWORD(v49[4]) = 11;
      if ( (Feature_CLAT_Preview2_RandomLocalAddress__private_featureState & 0x10) != 0 )
        v14 = Feature_CLAT_Preview2_RandomLocalAddress__private_featureState & 1;
      else
        v14 = Feature_CLAT_Preview2_RandomLocalAddress__private_IsEnabledDeviceUsageNoInline(v10, v9, v11, v12);
      if ( v14 )
      {
        v15 = *(_OWORD *)IPxlatResolveSyntheticIPv6Address(v40);
        v16 = &v45;
        v45 = v15;
      }
      else
      {
        v16 = (__int128 *)(a1 + 28);
      }
      *((_QWORD *)&v49[4] + 1) = v16;
      LODWORD(v49[6]) = 8;
      v49[5] = FWPM_CONDITION_FLAGS;
      DWORD2(v49[6]) = 3;
      LODWORD(v49[7]) = 32;
      v7 = FwpmFilterAdd0(engineHandle, &v42, 0, (UINT64 *)(a1 + 56));
      v5 = v7;
      if ( v7 >= 0 )
      {
        v43.displayData.name = L"IPxlatForwardIPv4filter";
        v43.layerKey = FWPM_LAYER_IPFORWARD_V4;
        v43.numFilterConditions = 2;
        v43.filterCondition = (FWPM_FILTER_CONDITION0 *)v47;
        v43.action.type = 20483;
        v43.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)IPXLAT_WFP_FORWARD_IPV4_LAYER_CALLOUT;
        v43.weight.type = FWP_UINT64;
        v43.subLayerKey = IPXLAT_WFP_FORWARD_IPV4_SUBLAYER;
        v43.weight.uint64 = (UINT64 *)&v39;
        memset(v47, 0, sizeof(v47));
        LODWORD(v47[2]) = *(_DWORD *)(a1 + 24);
        v17 = *(_DWORD *)(a1 + 80);
        v47[0] = FWPM_CONDITION_DESTINATION_INTERFACE_INDEX;
        LODWORD(v47[1]) = 0;
        DWORD2(v47[1]) = 3;
        *(GUID *)((char *)&v47[2] + 8) = FWPM_CONDITION_IP_SOURCE_ADDRESS;
        DWORD2(v47[3]) = 0;
        LODWORD(v47[4]) = 3;
        DWORD2(v47[4]) = _byteswap_ulong(v17);
        v7 = FwpmFilterAdd0(engineHandle, &v43, 0, (UINT64 *)(a1 + 64));
        v5 = v7;
        if ( v7 >= 0 )
        {
          if ( (Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_featureState & 0x10) != 0 )
            v18 = Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_featureState & 1;
          else
            v18 = Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_IsEnabledDeviceUsageNoInline();
          if ( !v18 )
            goto LABEL_30;
          v44.displayData.name = L"IPxlatOutboundEthernetFilter";
          v44.layerKey = (GUID)FWPM_LAYER_OUTBOUND_MAC_FRAME_ETHERNET;
          v44.numFilterConditions = 2;
          v44.filterCondition = (FWPM_FILTER_CONDITION0 *)v48;
          v44.action.type = 20483;
          v44.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)IPXLAT_WFP_OUTBOUND_ETHERNET_LAYER_CALLOUT;
          v44.weight.type = FWP_UINT64;
          v44.subLayerKey = IPXLAT_WFP_OUTBOUND_ETHERNET_SUBLAYER;
          v44.weight.uint64 = (UINT64 *)&v39;
          memset(v48, 0, sizeof(v48));
          v19 = *(_DWORD *)(a1 + 24);
          v48[0] = FWPM_CONDITION_INTERFACE_INDEX;
          LODWORD(v48[2]) = v19;
          LODWORD(v48[1]) = 0;
          DWORD2(v48[1]) = 3;
          *(_OWORD *)((char *)&v48[2] + 8) = FWPM_CONDITION_ETHER_TYPE;
          DWORD2(v48[3]) = 0;
          LODWORD(v48[4]) = 2;
          WORD4(v48[4]) = 2054;
          v7 = FwpmFilterAdd0(engineHandle, &v44, 0, (UINT64 *)(a1 + 72));
          v5 = v7;
          if ( v7 >= 0 )
          {
LABEL_30:
            FwpmTransactionCommit0(engineHandle);
            goto LABEL_51;
          }
          if ( (xmmword_1400272D0 & 2) == 0 )
            goto LABEL_29;
          v8 = 26;
          goto LABEL_28;
        }
        if ( (xmmword_1400272D0 & 2) != 0 )
        {
          v8 = 25;
          goto LABEL_28;
        }
      }
      else if ( (xmmword_1400272D0 & 2) != 0 )
      {
        v8 = 24;
        goto LABEL_28;
      }
    }
    else if ( (xmmword_1400272D0 & 2) != 0 )
    {
      v8 = 23;
LABEL_28:
      WPP_SF_d(513, v8, WPP_b58024cfe01b3143f1c8b927d5346b48_Traceguids, (unsigned int)v7);
    }
LABEL_29:
    FwpmTransactionAbort0(engineHandle);
    goto LABEL_51;
  }
  if ( (xmmword_1400272D0 & 2) != 0 )
    WPP_SF_d(513, 22, WPP_b58024cfe01b3143f1c8b927d5346b48_Traceguids, (unsigned int)v4);
LABEL_52:
  if ( (xmmword_1400272E0 & 2) != 0 )
    WPP_SF_d(1025, 27, WPP_b58024cfe01b3143f1c8b927d5346b48_Traceguids, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400177b8  mov     [rsp-8+arg_8], rbx
0x1400177bd  mov     [rsp-8+arg_10], rdi
0x1400177c2  push    rbp
0x1400177c3  push    r12
0x1400177c5  push    r13
0x1400177c7  push    r14
0x1400177c9  push    r15
0x1400177cb  lea     rbp, [rsp-420h]
0x1400177d3  sub     rsp, 520h
0x1400177da  mov     rax, cs:__security_cookie
0x1400177e1  xor     rax, rsp
0x1400177e4  mov     [rbp+440h+var_30], rax
0x1400177eb  xor     r15d, r15d
0x1400177ee  lea     rax, [rsp+540h+var_510]
0x1400177f3  mov     r14b, dl
0x1400177f6  mov     [rsp+540h+var_510], r15
0x1400177fb  mov     rdi, rcx
0x1400177fe  mov     [rsp+540h+engineHandle], rax; engineHandle
0x140017803  xorps   xmm0, xmm0
0x140017806  xor     r9d, r9d; session
0x140017809  lea     edx, [r15+0Ah]; authnService
0x14001780d  xor     r8d, r8d; authIdentity
0x140017810  xor     ecx, ecx; serverName
0x140017812  movups  [rbp+440h+var_1B0], xmm0
0x140017819  call    cs:__imp_FwpmEngineOpen0
0x140017820  nop     dword ptr [rax+rax+00h]
0x140017825  lea     r12, WPP_b58024cfe01b3143f1c8b927d5346b48_Traceguids
0x14001782c  mov     ebx, eax
0x14001782e  test    eax, eax
0x140017830  jns     short loc_140017858
0x140017832  test    byte ptr cs:xmmword_1400272D0, 2
0x140017839  jz      loc_140017E6B
0x14001783f  lea     edx, [r15+16h]
0x140017843  mov     ecx, 201h
0x140017848  mov     r9d, eax
0x14001784b  mov     r8, r12
0x14001784e  call    WPP_SF_d
0x140017853  jmp     loc_140017E6B
0x140017858  test    r14b, r14b
0x14001785b  jz      loc_140017D9E
0x140017861  mov     ebx, 0C8h
0x140017866  lea     rcx, [rsp+540h+filter]; void *
0x14001786b  mov     r8d, ebx; Size
0x14001786e  xor     edx, edx; Val
0x140017870  call    memset
0x140017875  mov     r8d, ebx; Size
0x140017878  lea     rcx, [rbp+440h+var_420]; void *
0x14001787c  xor     edx, edx; Val
0x14001787e  call    memset
0x140017883  mov     r8d, ebx; Size
0x140017886  lea     rcx, [rbp+440h+var_350]; void *
0x14001788d  xor     edx, edx; Val
0x14001788f  call    memset
0x140017894  mov     r8d, ebx; Size
0x140017897  lea     rcx, [rbp+440h+var_280]; void *
0x14001789e  xor     edx, edx; Val
0x1400178a0  call    memset
0x1400178a5  mov     rcx, [rsp+540h+var_510]; engineHandle
0x1400178aa  xor     edx, edx; flags
0x1400178ac  mov     [rsp+540h+var_508], 0FFFFFFFFFFFFFFFCh
0x1400178b5  call    cs:__imp_FwpmTransactionBegin0
0x1400178bc  nop     dword ptr [rax+rax+00h]
0x1400178c1  mov     ebx, eax
0x1400178c3  test    eax, eax
0x1400178c5  js      loc_140017E5A
0x1400178cb  movups  xmm0, xmmword ptr cs:FWPM_LAYER_OUTBOUND_IPPACKET_V4.Data1
0x1400178d2  lea     rax, aIpxlatoutbound; "IPxlatOutboundIPv4filter"
0x1400178d9  xor     edx, edx; Val
0x1400178db  movups  xmm1, xmmword ptr cs:IPXLAT_WFP_OUTBOUND_IPV4_SUBLAYER.Data1
0x1400178e2  mov     [rsp+540h+filter.displayData.name], rax
0x1400178e7  lea     rcx, [rbp+440h+var_1A0]; void *
0x1400178ee  movdqu  xmmword ptr [rbp+440h+filter.layerKey.Data1], xmm0
0x1400178f3  lea     rax, [rbp+440h+var_1A0]
0x1400178fa  mov     [rbp+440h+filter.numFilterConditions], 2
0x140017901  movups  xmm0, cs:IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT
0x140017908  mov     [rbp+440h+filter.filterCondition], rax
0x14001790c  lea     r8d, [rdx+50h]; Size
0x140017910  lea     rax, [rsp+540h+var_508]
0x140017915  mov     [rbp+440h+filter.action.type], 5003h
0x14001791c  movdqu  xmmword ptr [rbp+440h+filter.action.4], xmm0
0x140017921  mov     [rbp+440h+filter.weight.type], 4
0x140017928  movdqu  xmmword ptr [rbp+440h+filter.subLayerKey.Data1], xmm1
0x14001792d  mov     qword ptr [rbp+440h+filter.weight.8], rax
0x140017931  call    memset
0x140017936  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_INTERFACE_INDEX.Data1
0x14001793d  mov     eax, [rdi+18h]
0x140017940  lea     r14, [rdi+50h]
0x140017944  mov     rcx, [rsp+540h+var_510]; engineHandle
0x140017949  lea     r9, [rdi+30h]; id
0x14001794d  mov     [rbp+440h+var_180], eax
0x140017953  lea     rdx, [rsp+540h+filter]; filter
0x140017958  mov     eax, [r14]
0x14001795b  mov     r13d, 3
0x140017961  movdqu  [rbp+440h+var_1A0], xmm0
0x140017969  bswap   eax
0x14001796b  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS.Data1
0x140017972  xor     r8d, r8d; sd
0x140017975  mov     [rbp+440h+var_190], r15d
0x14001797c  mov     [rbp+440h+var_188], r13d
0x140017983  movdqu  [rbp+440h+var_178], xmm0
0x14001798b  mov     [rbp+440h+var_168], r15d
0x140017992  mov     [rbp+440h+var_160], r13d
0x140017999  mov     [rbp+440h+var_158], eax
0x14001799f  call    cs:__imp_FwpmFilterAdd0
0x1400179a6  nop     dword ptr [rax+rax+00h]
0x1400179ab  mov     ebx, eax
0x1400179ad  test    eax, eax
0x1400179af  jns     short loc_1400179C7
0x1400179b1  test    byte ptr cs:xmmword_1400272D0, 2
0x1400179b8  jz      loc_140017D72
0x1400179be  lea     edx, [r13+14h]
0x1400179c2  jmp     loc_140017D62
0x1400179c7  movups  xmm0, xmmword ptr cs:FWPM_LAYER_INBOUND_IPPACKET_V6.Data1
0x1400179ce  lea     rax, aIpxlatinboundi; "IPxlatInboundIPv6filter"
0x1400179d5  xor     edx, edx; Val
0x1400179d7  movups  xmm1, xmmword ptr cs:IPXLAT_WFP_INBOUND_IPV6_SUBLAYER.Data1
0x1400179de  mov     [rbp+440h+var_420.displayData.name], rax
0x1400179e2  lea     rcx, [rbp+440h+var_B0]; void *
0x1400179e9  movdqu  xmmword ptr [rbp+440h+var_420.layerKey.Data1], xmm0
0x1400179ee  lea     rax, [rbp+440h+var_B0]
0x1400179f5  mov     [rbp+440h+var_420.numFilterConditions], r13d
0x1400179fc  movups  xmm0, cs:IPXLAT_WFP_INBOUND_IPV6_LAYER_CALLOUT
0x140017a03  mov     [rbp+440h+var_420.filterCondition], rax
0x140017a0a  lea     r8d, [rdx+78h]; Size
0x140017a0e  lea     rax, [rsp+540h+var_508]
0x140017a13  mov     [rbp+440h+var_420.action.type], 5003h
0x140017a1d  movdqu  xmmword ptr [rbp+440h+var_420.action.4], xmm0
0x140017a25  mov     [rbp+440h+var_420.weight.type], 4
0x140017a2f  movdqu  xmmword ptr [rbp+440h+var_420.subLayerKey.Data1], xmm1
0x140017a34  mov     qword ptr [rbp+440h+var_420.weight.8], rax
0x140017a3b  call    memset
0x140017a40  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_INTERFACE_INDEX.Data1
0x140017a47  mov     eax, [rdi+18h]
0x140017a4a  mov     [rbp+440h+var_A0], r15d
0x140017a51  movdqu  [rbp+440h+var_B0], xmm0
0x140017a59  mov     [rbp+440h+var_98], r13d
0x140017a60  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS.Data1
0x140017a67  mov     [rbp+440h+var_90], eax
0x140017a6d  mov     [rbp+440h+var_78], r15d
0x140017a74  movdqu  [rbp+440h+var_88], xmm0
0x140017a7c  mov     [rbp+440h+var_70], 0Bh
0x140017a86  mov     eax, cs:Feature_CLAT_Preview2_RandomLocalAddress__private_featureState
0x140017a8c  test    al, 10h
0x140017a8e  jz      short loc_140017A95
0x140017a90  and     eax, 1
0x140017a93  jmp     short loc_140017A9A
0x140017a95  call    Feature_CLAT_Preview2_RandomLocalAddress__private_IsEnabledDeviceUsageNoInline
0x140017a9a  test    eax, eax
0x140017a9c  jz      short loc_140017ABF
0x140017a9e  mov     rdx, r14
0x140017aa1  lea     rcx, [rsp+540h+var_500]; void *
0x140017aa6  call    IPxlatResolveSyntheticIPv6Address
0x140017aab  movups  xmm0, xmmword ptr [rax]
0x140017aae  lea     rax, [rbp+440h+var_1B0]
0x140017ab5  movdqu  [rbp+440h+var_1B0], xmm0
0x140017abd  jmp     short loc_140017AC3
0x140017abf  lea     rax, [rdi+1Ch]
0x140017ac3  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_FLAGS.Data1
0x140017aca  mov     rcx, [rsp+540h+var_510]; engineHandle
0x140017acf  lea     r9, [rdi+38h]; id
0x140017ad3  xor     r8d, r8d; sd
0x140017ad6  mov     [rbp+440h+var_68], rax
0x140017add  lea     rdx, [rbp+440h+var_420]; filter
0x140017ae1  mov     [rbp+440h+var_50], 8
0x140017aeb  movdqu  [rbp+440h+var_60], xmm0
0x140017af3  mov     [rbp+440h+var_48], r13d
0x140017afa  mov     [rbp+440h+var_40], 20h ; ' '
0x140017b04  call    cs:__imp_FwpmFilterAdd0
0x140017b0b  nop     dword ptr [rax+rax+00h]
0x140017b10  mov     ebx, eax
0x140017b12  test    eax, eax
0x140017b14  jns     short loc_140017B2D
0x140017b16  test    byte ptr cs:xmmword_1400272D0, 2
0x140017b1d  jz      loc_140017D72
0x140017b23  mov     edx, 18h
0x140017b28  jmp     loc_140017D62
0x140017b2d  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPFORWARD_V4.Data1
0x140017b34  lea     rax, aIpxlatforwardi; "IPxlatForwardIPv4filter"
0x140017b3b  xor     edx, edx; Val
0x140017b3d  movups  xmm1, xmmword ptr cs:IPXLAT_WFP_FORWARD_IPV4_SUBLAYER.Data1
0x140017b44  mov     [rbp+440h+var_350.displayData.name], rax
0x140017b4b  lea     rcx, [rbp+440h+var_150]; void *
0x140017b52  movdqu  xmmword ptr [rbp+440h+var_350.layerKey.Data1], xmm0
0x140017b5a  lea     rax, [rbp+440h+var_150]
0x140017b61  mov     [rbp+440h+var_350.numFilterConditions], 2
0x140017b6b  movups  xmm0, cs:IPXLAT_WFP_FORWARD_IPV4_LAYER_CALLOUT
0x140017b72  mov     [rbp+440h+var_350.filterCondition], rax
0x140017b79  lea     r8d, [rdx+50h]; Size
0x140017b7d  lea     rax, [rsp+540h+var_508]
0x140017b82  mov     [rbp+440h+var_350.action.type], 5003h
0x140017b8c  movdqu  xmmword ptr [rbp+440h+var_350.action.4], xmm0
0x140017b94  mov     [rbp+440h+var_350.weight.type], 4
0x140017b9e  movdqu  xmmword ptr [rbp+440h+var_350.subLayerKey.Data1], xmm1
0x140017ba6  mov     qword ptr [rbp+440h+var_350.weight.8], rax
0x140017bad  call    memset
0x140017bb2  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_DESTINATION_INTERFACE_INDEX.Data1
0x140017bb9  mov     eax, [rdi+18h]
0x140017bbc  lea     r9, [rdi+40h]; id
0x140017bc0  mov     rcx, [rsp+540h+var_510]; engineHandle
0x140017bc5  lea     rdx, [rbp+440h+var_350]; filter
0x140017bcc  mov     [rbp+440h+var_130], eax
0x140017bd2  xor     r8d, r8d; sd
0x140017bd5  mov     eax, [r14]
0x140017bd8  movdqu  [rbp+440h+var_150], xmm0
0x140017be0  bswap   eax
0x140017be2  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_SOURCE_ADDRESS.Data1
0x140017be9  mov     [rbp+440h+var_140], r15d
0x140017bf0  mov     [rbp+440h+var_138], r13d
0x140017bf7  movdqu  [rbp+440h+var_128], xmm0
0x140017bff  mov     [rbp+440h+var_118], r15d
0x140017c06  mov     [rbp+440h+var_110], r13d
0x140017c0d  mov     [rbp+440h+var_108], eax
0x140017c13  call    cs:__imp_FwpmFilterAdd0
0x140017c1a  nop     dword ptr [rax+rax+00h]
0x140017c1f  mov     ebx, eax
0x140017c21  test    eax, eax
0x140017c23  jns     short loc_140017C3C
0x140017c25  test    byte ptr cs:xmmword_1400272D0, 2
0x140017c2c  jz      loc_140017D72
0x140017c32  mov     edx, 19h
0x140017c37  jmp     loc_140017D62
0x140017c3c  mov     eax, cs:Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_featureState
0x140017c42  test    al, 10h
0x140017c44  jz      short loc_140017C4B
0x140017c46  and     eax, 1
0x140017c49  jmp     short loc_140017C50
0x140017c4b  call    Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_IsEnabledDeviceUsageNoInline
0x140017c50  test    eax, eax
0x140017c52  jz      loc_140017D88
0x140017c58  movups  xmm0, cs:FWPM_LAYER_OUTBOUND_MAC_FRAME_ETHERNET
0x140017c5f  lea     rax, aIpxlatoutbound_0; "IPxlatOutboundEthernetFilter"
0x140017c66  xor     edx, edx; Val
0x140017c68  movups  xmm1, xmmword ptr cs:IPXLAT_WFP_OUTBOUND_ETHERNET_SUBLAYER.Data1
0x140017c6f  mov     [rbp+440h+var_280.displayData.name], rax
0x140017c76  lea     rcx, [rbp+440h+var_100]; void *
0x140017c7d  movdqu  xmmword ptr [rbp+440h+var_280.layerKey.Data1], xmm0
0x140017c85  lea     rax, [rbp+440h+var_100]
0x140017c8c  mov     [rbp+440h+var_280.numFilterConditions], 2
0x140017c96  movups  xmm0, cs:IPXLAT_WFP_OUTBOUND_ETHERNET_LAYER_CALLOUT
0x140017c9d  mov     [rbp+440h+var_280.filterCondition], rax
0x140017ca4  lea     r8d, [rdx+50h]; Size
0x140017ca8  lea     rax, [rsp+540h+var_508]
0x140017cad  mov     [rbp+440h+var_280.action.type], 5003h
0x140017cb7  movdqu  xmmword ptr [rbp+440h+var_280.action.4], xmm0
0x140017cbf  mov     [rbp+440h+var_280.weight.type], 4
0x140017cc9  movdqu  xmmword ptr [rbp+440h+var_280.subLayerKey.Data1], xmm1
0x140017cd1  mov     qword ptr [rbp+440h+var_280.weight.8], rax
0x140017cd8  call    memset
0x140017cdd  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_INTERFACE_INDEX.Data1
0x140017ce4  mov     eax, [rdi+18h]
0x140017ce7  lea     r9, [rdi+48h]; id
0x140017ceb  mov     rcx, [rsp+540h+var_510]; engineHandle
0x140017cf0  lea     rdx, [rbp+440h+var_280]; filter
0x140017cf7  movdqu  [rbp+440h+var_100], xmm0
0x140017cff  mov     [rbp+440h+var_E0], eax
0x140017d05  mov     eax, 806h
0x140017d0a  movups  xmm0, cs:FWPM_CONDITION_ETHER_TYPE
0x140017d11  xor     r8d, r8d; sd
0x140017d14  mov     [rbp+440h+var_F0], r15d
0x140017d1b  mov     [rbp+440h+var_E8], r13d
0x140017d22  movdqu  [rbp+440h+var_D8], xmm0
0x140017d2a  mov     [rbp+440h+var_C8], r15d
0x140017d31  mov     [rbp+440h+var_C0], 2
0x140017d3b  mov     [rbp+440h+var_B8], ax
0x140017d42  call    cs:__imp_FwpmFilterAdd0
0x140017d49  nop     dword ptr [rax+rax+00h]
0x140017d4e  mov     ebx, eax
0x140017d50  test    eax, eax
0x140017d52  jns     short loc_140017D88
0x140017d54  test    byte ptr cs:xmmword_1400272D0, 2
0x140017d5b  jz      short loc_140017D72
0x140017d5d  mov     edx, 1Ah
0x140017d62  mov     r9d, eax
0x140017d65  mov     r8, r12
0x140017d68  mov     ecx, 201h
0x140017d6d  call    WPP_SF_d
0x140017d72  mov     rcx, [rsp+540h+var_510]; engineHandle
0x140017d77  call    cs:__imp_FwpmTransactionAbort0
0x140017d7e  nop     dword ptr [rax+rax+00h]
0x140017d83  jmp     loc_140017E5A
0x140017d88  mov     rcx, [rsp+540h+var_510]; engineHandle
0x140017d8d  call    cs:__imp_FwpmTransactionCommit0
0x140017d94  nop     dword ptr [rax+rax+00h]
0x140017d99  jmp     loc_140017E5A
0x140017d9e  mov     rdx, [rdi+30h]; id
0x140017da2  test    rdx, rdx
0x140017da5  jz      short loc_140017DC7
0x140017da7  mov     rcx, [rsp+540h+var_510]; engineHandle
0x140017dac  call    cs:__imp_FwpmFilterDeleteById0
0x140017db3  nop     dword ptr [rax+rax+00h]
0x140017db8  mov     ebx, eax
0x140017dba  test    eax, eax
0x140017dbc  jns     short loc_140017DC3
0x140017dbe  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140017dc3  mov     [rdi+30h], r15
0x140017dc7  mov     rdx, [rdi+38h]; id
0x140017dcb  test    rdx, rdx
0x140017dce  jz      short loc_140017DF0
0x140017dd0  mov     rcx, [rsp+540h+var_510]; engineHandle
0x140017dd5  call    cs:__imp_FwpmFilterDeleteById0
  ... truncated ...
```
