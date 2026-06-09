# IPxlatConfigureFiltersForInstance

- ea: `0x140016aec`
- end: `0x14001718a`
- name: `IPxlatConfigureFiltersForInstance`
- size: `1694`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140015b28`
- `0x140015eb8`
- `0x14001784c`

## callees

- `0x14000caa0`
- `0x140016310`
- `0x140016aec`
- `0x14001ede0`
- `0x14001f440`
- `0x14002d008`

## import_xrefs

- `fwpkclnt!FwpmTransactionAbort0` at `0x140017055`
- `fwpkclnt!FwpmTransactionAbort0` at `0x140017055`
- `fwpkclnt!FwpmTransactionBegin0` at `0x140016bd6`
- `fwpkclnt!FwpmTransactionBegin0` at `0x140016bd6`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x14001708a`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x1400170b3`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x1400170dc`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x14001711d`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x14001708a`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x1400170b3`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x1400170dc`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x14001711d`
- `fwpkclnt!FwpmFilterAdd0` at `0x140016cbc`
- `fwpkclnt!FwpmFilterAdd0` at `0x140016de2`
- `fwpkclnt!FwpmFilterAdd0` at `0x140016ef1`
- `fwpkclnt!FwpmFilterAdd0` at `0x140017020`
- `fwpkclnt!FwpmFilterAdd0` at `0x140016cbc`
- `fwpkclnt!FwpmFilterAdd0` at `0x140016de2`
- `fwpkclnt!FwpmFilterAdd0` at `0x140016ef1`
- `fwpkclnt!FwpmFilterAdd0` at `0x140017020`
- `fwpkclnt!FwpmEngineClose0` at `0x14001713d`
- `fwpkclnt!FwpmEngineClose0` at `0x14001713d`
- `fwpkclnt!FwpmEngineOpen0` at `0x140016b3a`
- `fwpkclnt!FwpmEngineOpen0` at `0x140016b3a`
- `fwpkclnt!FwpmTransactionCommit0` at `0x14001706b`
- `fwpkclnt!FwpmTransactionCommit0` at `0x14001706b`

## pseudocode

```c
__int64 __fastcall IPxlatConfigureFiltersForInstance(__int64 a1, char a2)
{
  NTSTATUS v4; // eax
  NTSTATUS v5; // ebx
  unsigned int v6; // eax
  NTSTATUS v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  unsigned int v10; // eax
  int v11; // eax
  int v12; // eax
  UINT64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  UINT64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  UINT64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  int IsEnabledDeviceUsageNoInline; // eax
  UINT64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  HANDLE engineHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  FWPM_FILTER0 filter; // [rsp+40h] [rbp-C0h] BYREF
  FWPM_FILTER0 v38; // [rsp+110h] [rbp+10h] BYREF
  FWPM_FILTER0 v39; // [rsp+1E0h] [rbp+E0h] BYREF
  FWPM_FILTER0 v40; // [rsp+2B0h] [rbp+1B0h] BYREF
  _OWORD v41[5]; // [rsp+380h] [rbp+280h] BYREF
  _OWORD v42[5]; // [rsp+3D0h] [rbp+2D0h] BYREF
  _OWORD v43[5]; // [rsp+420h] [rbp+320h] BYREF
  _OWORD v44[8]; // [rsp+470h] [rbp+370h] BYREF

  engineHandle = 0;
  v4 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( !a2 )
    {
      v13 = *(_QWORD *)(a1 + 48);
      if ( v13 )
      {
        v5 = FwpmFilterDeleteById0(engineHandle, v13);
        if ( v5 < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v15, v14, v16, v17);
        *(_QWORD *)(a1 + 48) = 0;
      }
      v18 = *(_QWORD *)(a1 + 56);
      if ( v18 )
      {
        v5 = FwpmFilterDeleteById0(engineHandle, v18);
        if ( v5 < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v20, v19, v21, v22);
        *(_QWORD *)(a1 + 56) = 0;
      }
      v23 = *(_QWORD *)(a1 + 64);
      if ( v23 )
      {
        v5 = FwpmFilterDeleteById0(engineHandle, v23);
        if ( v5 < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v25, v24, v26, v27);
        *(_QWORD *)(a1 + 64) = 0;
      }
      if ( (Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_featureState & 0x10) != 0 )
        IsEnabledDeviceUsageNoInline = Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_featureState & 1;
      else
        IsEnabledDeviceUsageNoInline = Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_IsEnabledDeviceUsageNoInline();
      if ( IsEnabledDeviceUsageNoInline )
      {
        v29 = *(_QWORD *)(a1 + 72);
        if ( v29 )
        {
          v5 = FwpmFilterDeleteById0(engineHandle, v29);
          if ( v5 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgsKM(v31, v30, v32, v33);
          *(_QWORD *)(a1 + 72) = 0;
        }
      }
      goto LABEL_45;
    }
    memset(&filter, 0, sizeof(filter));
    memset(&v38, 0, sizeof(v38));
    memset(&v39, 0, sizeof(v39));
    memset(&v40, 0, sizeof(v40));
    v36 = -4;
    v5 = FwpmTransactionBegin0(engineHandle, 0);
    if ( v5 < 0 )
    {
LABEL_45:
      FwpmEngineClose0(engineHandle);
      goto LABEL_46;
    }
    filter.displayData.name = L"IPxlatOutboundIPv4filter";
    filter.layerKey = FWPM_LAYER_OUTBOUND_IPPACKET_V4;
    filter.numFilterConditions = 2;
    filter.filterCondition = (FWPM_FILTER_CONDITION0 *)v41;
    filter.action.type = 20483;
    filter.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT;
    filter.weight.type = FWP_UINT64;
    filter.subLayerKey = IPXLAT_WFP_OUTBOUND_IPV4_SUBLAYER;
    filter.weight.uint64 = (UINT64 *)&v36;
    memset(v41, 0, sizeof(v41));
    LODWORD(v41[2]) = *(_DWORD *)(a1 + 24);
    v6 = *(_DWORD *)(a1 + 80);
    v41[0] = FWPM_CONDITION_INTERFACE_INDEX;
    LODWORD(v41[1]) = 0;
    DWORD2(v41[1]) = 3;
    *(GUID *)((char *)&v41[2] + 8) = FWPM_CONDITION_IP_LOCAL_ADDRESS;
    DWORD2(v41[3]) = 0;
    LODWORD(v41[4]) = 3;
    DWORD2(v41[4]) = _byteswap_ulong(v6);
    v7 = FwpmFilterAdd0(engineHandle, &filter, 0, (UINT64 *)(a1 + 48));
    v5 = v7;
    if ( v7 >= 0 )
    {
      v38.displayData.name = L"IPxlatInboundIPv6filter";
      v38.layerKey = FWPM_LAYER_INBOUND_IPPACKET_V6;
      v38.numFilterConditions = 3;
      v38.filterCondition = (FWPM_FILTER_CONDITION0 *)v44;
      v38.action.type = 20483;
      v38.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)IPXLAT_WFP_INBOUND_IPV6_LAYER_CALLOUT;
      v38.weight.type = FWP_UINT64;
      v38.subLayerKey = IPXLAT_WFP_INBOUND_IPV6_SUBLAYER;
      v38.weight.uint64 = (UINT64 *)&v36;
      memset(v44, 0, 0x78u);
      v9 = *(_DWORD *)(a1 + 24);
      v44[0] = FWPM_CONDITION_INTERFACE_INDEX;
      LODWORD(v44[2]) = v9;
      LODWORD(v44[1]) = 0;
      DWORD2(v44[1]) = 3;
      *(GUID *)((char *)&v44[2] + 8) = FWPM_CONDITION_IP_LOCAL_ADDRESS;
      DWORD2(v44[3]) = 0;
      LODWORD(v44[4]) = 11;
      *((_QWORD *)&v44[4] + 1) = a1 + 28;
      v44[5] = FWPM_CONDITION_FLAGS;
      LODWORD(v44[6]) = 8;
      DWORD2(v44[6]) = 3;
      LODWORD(v44[7]) = 32;
      v7 = FwpmFilterAdd0(engineHandle, &v38, 0, (UINT64 *)(a1 + 56));
      v5 = v7;
      if ( v7 >= 0 )
      {
        v39.displayData.name = L"IPxlatForwardIPv4filter";
        v39.layerKey = FWPM_LAYER_IPFORWARD_V4;
        v39.numFilterConditions = 2;
        v39.filterCondition = (FWPM_FILTER_CONDITION0 *)v42;
        v39.action.type = 20483;
        v39.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)IPXLAT_WFP_FORWARD_IPV4_LAYER_CALLOUT;
        v39.weight.type = FWP_UINT64;
        v39.subLayerKey = IPXLAT_WFP_FORWARD_IPV4_SUBLAYER;
        v39.weight.uint64 = (UINT64 *)&v36;
        memset(v42, 0, sizeof(v42));
        LODWORD(v42[2]) = *(_DWORD *)(a1 + 24);
        v10 = *(_DWORD *)(a1 + 80);
        v42[0] = FWPM_CONDITION_DESTINATION_INTERFACE_INDEX;
        LODWORD(v42[1]) = 0;
        DWORD2(v42[1]) = 3;
        *(GUID *)((char *)&v42[2] + 8) = FWPM_CONDITION_IP_SOURCE_ADDRESS;
        DWORD2(v42[3]) = 0;
        LODWORD(v42[4]) = 3;
        DWORD2(v42[4]) = _byteswap_ulong(v10);
        v7 = FwpmFilterAdd0(engineHandle, &v39, 0, (UINT64 *)(a1 + 64));
        v5 = v7;
        if ( v7 >= 0 )
        {
          if ( (Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_featureState & 0x10) != 0 )
            v11 = Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_featureState & 1;
          else
            v11 = Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_IsEnabledDeviceUsageNoInline();
          if ( !v11 )
            goto LABEL_24;
          v40.displayData.name = L"IPxlatOutboundEthernetFilter";
          v40.layerKey = (GUID)FWPM_LAYER_OUTBOUND_MAC_FRAME_ETHERNET;
          v40.numFilterConditions = 2;
          v40.filterCondition = (FWPM_FILTER_CONDITION0 *)v43;
          v40.action.type = 20483;
          v40.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)IPXLAT_WFP_OUTBOUND_ETHERNET_LAYER_CALLOUT;
          v40.weight.type = FWP_UINT64;
          v40.subLayerKey = IPXLAT_WFP_OUTBOUND_ETHERNET_SUBLAYER;
          v40.weight.uint64 = (UINT64 *)&v36;
          memset(v43, 0, sizeof(v43));
          v12 = *(_DWORD *)(a1 + 24);
          v43[0] = FWPM_CONDITION_INTERFACE_INDEX;
          LODWORD(v43[2]) = v12;
          LODWORD(v43[1]) = 0;
          DWORD2(v43[1]) = 3;
          *(_OWORD *)((char *)&v43[2] + 8) = FWPM_CONDITION_ETHER_TYPE;
          DWORD2(v43[3]) = 0;
          LODWORD(v43[4]) = 2;
          WORD4(v43[4]) = 2054;
          v7 = FwpmFilterAdd0(engineHandle, &v40, 0, (UINT64 *)(a1 + 72));
          v5 = v7;
          if ( v7 >= 0 )
          {
LABEL_24:
            FwpmTransactionCommit0(engineHandle);
            goto LABEL_45;
          }
          if ( (xmmword_1400262D0 & 2) == 0 )
            goto LABEL_23;
          v8 = 26;
          goto LABEL_22;
        }
        if ( (xmmword_1400262D0 & 2) != 0 )
        {
          v8 = 25;
          goto LABEL_22;
        }
      }
      else if ( (xmmword_1400262D0 & 2) != 0 )
      {
        v8 = 24;
        goto LABEL_22;
      }
    }
    else if ( (xmmword_1400262D0 & 2) != 0 )
    {
      v8 = 23;
LABEL_22:
      WPP_SF_d(513, v8, WPP_639724ddcd2939a457521487d2ab8eb6_Traceguids, (unsigned int)v7);
    }
LABEL_23:
    FwpmTransactionAbort0(engineHandle);
    goto LABEL_45;
  }
  if ( (xmmword_1400262D0 & 2) != 0 )
    WPP_SF_d(513, 22, WPP_639724ddcd2939a457521487d2ab8eb6_Traceguids, (unsigned int)v4);
LABEL_46:
  if ( (xmmword_1400262E0 & 2) != 0 )
    WPP_SF_d(1025, 27, WPP_639724ddcd2939a457521487d2ab8eb6_Traceguids, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140016aec  push    rbp
0x140016aee  push    rbx
0x140016aef  push    rdi
0x140016af0  push    r12
0x140016af2  push    r14
0x140016af4  push    r15
0x140016af6  lea     rbp, [rsp-408h]
0x140016afe  sub     rsp, 508h
0x140016b05  mov     rax, cs:__security_cookie
0x140016b0c  xor     rax, rsp
0x140016b0f  mov     [rbp+430h+var_40], rax
0x140016b16  xor     r15d, r15d
0x140016b19  lea     rax, [rsp+530h+var_500]
0x140016b1e  mov     r14b, dl
0x140016b21  mov     [rsp+530h+var_500], r15
0x140016b26  mov     rdi, rcx
0x140016b29  mov     [rsp+530h+engineHandle], rax; engineHandle
0x140016b2e  xor     r9d, r9d; session
0x140016b31  xor     r8d, r8d; authIdentity
0x140016b34  lea     edx, [r15+0Ah]; authnService
0x140016b38  xor     ecx, ecx; serverName
0x140016b3a  call    cs:__imp_FwpmEngineOpen0
0x140016b41  nop     dword ptr [rax+rax+00h]
0x140016b46  lea     r12, WPP_639724ddcd2939a457521487d2ab8eb6_Traceguids
0x140016b4d  mov     ebx, eax
0x140016b4f  test    eax, eax
0x140016b51  jns     short loc_140016B79
0x140016b53  test    byte ptr cs:xmmword_1400262D0, 2
0x140016b5a  jz      loc_140017149
0x140016b60  lea     edx, [r15+16h]
0x140016b64  mov     ecx, 201h
0x140016b69  mov     r9d, eax
0x140016b6c  mov     r8, r12
0x140016b6f  call    WPP_SF_d
0x140016b74  jmp     loc_140017149
0x140016b79  test    r14b, r14b
0x140016b7c  jz      loc_14001707C
0x140016b82  mov     ebx, 0C8h
0x140016b87  lea     rcx, [rsp+530h+filter]; void *
0x140016b8c  mov     r8d, ebx; Size
0x140016b8f  xor     edx, edx; Val
0x140016b91  call    memset
0x140016b96  mov     r8d, ebx; Size
0x140016b99  lea     rcx, [rbp+430h+var_420]; void *
0x140016b9d  xor     edx, edx; Val
0x140016b9f  call    memset
0x140016ba4  mov     r8d, ebx; Size
0x140016ba7  lea     rcx, [rbp+430h+var_350]; void *
0x140016bae  xor     edx, edx; Val
0x140016bb0  call    memset
0x140016bb5  mov     r8d, ebx; Size
0x140016bb8  lea     rcx, [rbp+430h+var_280]; void *
0x140016bbf  xor     edx, edx; Val
0x140016bc1  call    memset
0x140016bc6  mov     rcx, [rsp+530h+var_500]; engineHandle
0x140016bcb  xor     edx, edx; flags
0x140016bcd  mov     [rsp+530h+var_4F8], 0FFFFFFFFFFFFFFFCh
0x140016bd6  call    cs:__imp_FwpmTransactionBegin0
0x140016bdd  nop     dword ptr [rax+rax+00h]
0x140016be2  mov     ebx, eax
0x140016be4  test    eax, eax
0x140016be6  js      loc_140017138
0x140016bec  movups  xmm0, xmmword ptr cs:FWPM_LAYER_OUTBOUND_IPPACKET_V4.Data1
0x140016bf3  lea     rax, aIpxlatoutbound; "IPxlatOutboundIPv4filter"
0x140016bfa  xor     edx, edx; Val
0x140016bfc  movups  xmm1, xmmword ptr cs:IPXLAT_WFP_OUTBOUND_IPV4_SUBLAYER.Data1
0x140016c03  mov     [rsp+530h+filter.displayData.name], rax
0x140016c08  lea     rcx, [rbp+430h+var_1B0]; void *
0x140016c0f  movdqu  xmmword ptr [rbp+430h+filter.layerKey.Data1], xmm0
0x140016c14  lea     rax, [rbp+430h+var_1B0]
0x140016c1b  mov     [rbp+430h+filter.numFilterConditions], 2
0x140016c22  movups  xmm0, cs:IPXLAT_WFP_OUTBOUND_IPV4_LAYER_CALLOUT
0x140016c29  mov     [rbp+430h+filter.filterCondition], rax
0x140016c2d  lea     r8d, [rdx+50h]; Size
0x140016c31  lea     rax, [rsp+530h+var_4F8]
0x140016c36  mov     [rbp+430h+filter.action.type], 5003h
0x140016c3d  movdqu  xmmword ptr [rbp+430h+filter.action.4], xmm0
0x140016c42  mov     [rbp+430h+filter.weight.type], 4
0x140016c49  movdqu  xmmword ptr [rbp+430h+filter.subLayerKey.Data1], xmm1
0x140016c4e  mov     qword ptr [rbp+430h+filter.weight.8], rax
0x140016c52  call    memset
0x140016c57  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_INTERFACE_INDEX.Data1
0x140016c5e  mov     eax, [rdi+18h]
0x140016c61  lea     r9, [rdi+30h]; id
0x140016c65  mov     rcx, [rsp+530h+var_500]; engineHandle
0x140016c6a  lea     rdx, [rsp+530h+filter]; filter
0x140016c6f  mov     [rbp+430h+var_190], eax
0x140016c75  mov     r14d, 3
0x140016c7b  mov     eax, [rdi+50h]
0x140016c7e  xor     r8d, r8d; sd
0x140016c81  movdqu  [rbp+430h+var_1B0], xmm0
0x140016c89  bswap   eax
0x140016c8b  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS.Data1
0x140016c92  mov     [rbp+430h+var_1A0], r15d
0x140016c99  mov     [rbp+430h+var_198], r14d
0x140016ca0  movdqu  [rbp+430h+var_188], xmm0
0x140016ca8  mov     [rbp+430h+var_178], r15d
0x140016caf  mov     [rbp+430h+var_170], r14d
0x140016cb6  mov     [rbp+430h+var_168], eax
0x140016cbc  call    cs:__imp_FwpmFilterAdd0
0x140016cc3  nop     dword ptr [rax+rax+00h]
0x140016cc8  mov     ebx, eax
0x140016cca  test    eax, eax
0x140016ccc  jns     short loc_140016CE4
0x140016cce  test    byte ptr cs:xmmword_1400262D0, 2
0x140016cd5  jz      loc_140017050
0x140016cdb  lea     edx, [r14+14h]
0x140016cdf  jmp     loc_140017040
0x140016ce4  movups  xmm0, xmmword ptr cs:FWPM_LAYER_INBOUND_IPPACKET_V6.Data1
0x140016ceb  lea     rax, aIpxlatinboundi; "IPxlatInboundIPv6filter"
0x140016cf2  xor     edx, edx; Val
0x140016cf4  movups  xmm1, xmmword ptr cs:IPXLAT_WFP_INBOUND_IPV6_SUBLAYER.Data1
0x140016cfb  mov     [rbp+430h+var_420.displayData.name], rax
0x140016cff  lea     rcx, [rbp+430h+var_C0]; void *
0x140016d06  movdqu  xmmword ptr [rbp+430h+var_420.layerKey.Data1], xmm0
0x140016d0b  lea     rax, [rbp+430h+var_C0]
0x140016d12  mov     [rbp+430h+var_420.numFilterConditions], r14d
0x140016d19  movups  xmm0, cs:IPXLAT_WFP_INBOUND_IPV6_LAYER_CALLOUT
0x140016d20  mov     [rbp+430h+var_420.filterCondition], rax
0x140016d27  lea     r8d, [rdx+78h]; Size
0x140016d2b  lea     rax, [rsp+530h+var_4F8]
0x140016d30  mov     [rbp+430h+var_420.action.type], 5003h
0x140016d3a  movdqu  xmmword ptr [rbp+430h+var_420.action.4], xmm0
0x140016d42  mov     [rbp+430h+var_420.weight.type], 4
0x140016d49  movdqu  xmmword ptr [rbp+430h+var_420.subLayerKey.Data1], xmm1
0x140016d4e  mov     qword ptr [rbp+430h+var_420.weight.8], rax
0x140016d52  call    memset
0x140016d57  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_INTERFACE_INDEX.Data1
0x140016d5e  mov     eax, [rdi+18h]
0x140016d61  lea     r9, [rdi+38h]; id
0x140016d65  mov     rcx, [rsp+530h+var_500]; engineHandle
0x140016d6a  lea     rdx, [rbp+430h+var_420]; filter
0x140016d6e  movdqu  [rbp+430h+var_C0], xmm0
0x140016d76  mov     [rbp+430h+var_A0], eax
0x140016d7c  lea     rax, [rdi+1Ch]
0x140016d80  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS.Data1
0x140016d87  xor     r8d, r8d; sd
0x140016d8a  mov     [rbp+430h+var_B0], r15d
0x140016d91  mov     [rbp+430h+var_A8], r14d
0x140016d98  movdqu  [rbp+430h+var_98], xmm0
0x140016da0  mov     [rbp+430h+var_88], r15d
0x140016da7  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_FLAGS.Data1
0x140016dae  mov     [rbp+430h+var_80], 0Bh
0x140016db8  mov     [rbp+430h+var_78], rax
0x140016dbf  movdqu  [rbp+430h+var_70], xmm0
0x140016dc7  mov     [rbp+430h+var_60], 8
0x140016dd1  mov     [rbp+430h+var_58], r14d
0x140016dd8  mov     [rbp+430h+var_50], 20h ; ' '
0x140016de2  call    cs:__imp_FwpmFilterAdd0
0x140016de9  nop     dword ptr [rax+rax+00h]
0x140016dee  mov     ebx, eax
0x140016df0  test    eax, eax
0x140016df2  jns     short loc_140016E0B
0x140016df4  test    byte ptr cs:xmmword_1400262D0, 2
0x140016dfb  jz      loc_140017050
0x140016e01  mov     edx, 18h
0x140016e06  jmp     loc_140017040
0x140016e0b  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPFORWARD_V4.Data1
0x140016e12  lea     rax, aIpxlatforwardi; "IPxlatForwardIPv4filter"
0x140016e19  xor     edx, edx; Val
0x140016e1b  movups  xmm1, xmmword ptr cs:IPXLAT_WFP_FORWARD_IPV4_SUBLAYER.Data1
0x140016e22  mov     [rbp+430h+var_350.displayData.name], rax
0x140016e29  lea     rcx, [rbp+430h+var_160]; void *
0x140016e30  movdqu  xmmword ptr [rbp+430h+var_350.layerKey.Data1], xmm0
0x140016e38  lea     rax, [rbp+430h+var_160]
0x140016e3f  mov     [rbp+430h+var_350.numFilterConditions], 2
0x140016e49  movups  xmm0, cs:IPXLAT_WFP_FORWARD_IPV4_LAYER_CALLOUT
0x140016e50  mov     [rbp+430h+var_350.filterCondition], rax
0x140016e57  lea     r8d, [rdx+50h]; Size
0x140016e5b  lea     rax, [rsp+530h+var_4F8]
0x140016e60  mov     [rbp+430h+var_350.action.type], 5003h
0x140016e6a  movdqu  xmmword ptr [rbp+430h+var_350.action.4], xmm0
0x140016e72  mov     [rbp+430h+var_350.weight.type], 4
0x140016e7c  movdqu  xmmword ptr [rbp+430h+var_350.subLayerKey.Data1], xmm1
0x140016e84  mov     qword ptr [rbp+430h+var_350.weight.8], rax
0x140016e8b  call    memset
0x140016e90  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_DESTINATION_INTERFACE_INDEX.Data1
0x140016e97  mov     eax, [rdi+18h]
0x140016e9a  lea     r9, [rdi+40h]; id
0x140016e9e  mov     rcx, [rsp+530h+var_500]; engineHandle
0x140016ea3  lea     rdx, [rbp+430h+var_350]; filter
0x140016eaa  mov     [rbp+430h+var_140], eax
0x140016eb0  xor     r8d, r8d; sd
0x140016eb3  mov     eax, [rdi+50h]
0x140016eb6  movdqu  [rbp+430h+var_160], xmm0
0x140016ebe  bswap   eax
0x140016ec0  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_SOURCE_ADDRESS.Data1
0x140016ec7  mov     [rbp+430h+var_150], r15d
0x140016ece  mov     [rbp+430h+var_148], r14d
0x140016ed5  movdqu  [rbp+430h+var_138], xmm0
0x140016edd  mov     [rbp+430h+var_128], r15d
0x140016ee4  mov     [rbp+430h+var_120], r14d
0x140016eeb  mov     [rbp+430h+var_118], eax
0x140016ef1  call    cs:__imp_FwpmFilterAdd0
0x140016ef8  nop     dword ptr [rax+rax+00h]
0x140016efd  mov     ebx, eax
0x140016eff  test    eax, eax
0x140016f01  jns     short loc_140016F1A
0x140016f03  test    byte ptr cs:xmmword_1400262D0, 2
0x140016f0a  jz      loc_140017050
0x140016f10  mov     edx, 19h
0x140016f15  jmp     loc_140017040
0x140016f1a  mov     eax, cs:Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_featureState
0x140016f20  test    al, 10h
0x140016f22  jz      short loc_140016F29
0x140016f24  and     eax, 1
0x140016f27  jmp     short loc_140016F2E
0x140016f29  call    Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_IsEnabledDeviceUsageNoInline
0x140016f2e  test    eax, eax
0x140016f30  jz      loc_140017066
0x140016f36  movups  xmm0, cs:FWPM_LAYER_OUTBOUND_MAC_FRAME_ETHERNET
0x140016f3d  lea     rax, aIpxlatoutbound_0; "IPxlatOutboundEthernetFilter"
0x140016f44  xor     edx, edx; Val
0x140016f46  movups  xmm1, xmmword ptr cs:IPXLAT_WFP_OUTBOUND_ETHERNET_SUBLAYER.Data1
0x140016f4d  mov     [rbp+430h+var_280.displayData.name], rax
0x140016f54  lea     rcx, [rbp+430h+var_110]; void *
0x140016f5b  movdqu  xmmword ptr [rbp+430h+var_280.layerKey.Data1], xmm0
0x140016f63  lea     rax, [rbp+430h+var_110]
0x140016f6a  mov     [rbp+430h+var_280.numFilterConditions], 2
0x140016f74  movups  xmm0, cs:IPXLAT_WFP_OUTBOUND_ETHERNET_LAYER_CALLOUT
0x140016f7b  mov     [rbp+430h+var_280.filterCondition], rax
0x140016f82  lea     r8d, [rdx+50h]; Size
0x140016f86  lea     rax, [rsp+530h+var_4F8]
0x140016f8b  mov     [rbp+430h+var_280.action.type], 5003h
0x140016f95  movdqu  xmmword ptr [rbp+430h+var_280.action.4], xmm0
0x140016f9d  mov     [rbp+430h+var_280.weight.type], 4
0x140016fa7  movdqu  xmmword ptr [rbp+430h+var_280.subLayerKey.Data1], xmm1
0x140016faf  mov     qword ptr [rbp+430h+var_280.weight.8], rax
0x140016fb6  call    memset
0x140016fbb  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_INTERFACE_INDEX.Data1
0x140016fc2  mov     eax, [rdi+18h]
0x140016fc5  lea     r9, [rdi+48h]; id
0x140016fc9  mov     rcx, [rsp+530h+var_500]; engineHandle
0x140016fce  lea     rdx, [rbp+430h+var_280]; filter
0x140016fd5  movdqu  [rbp+430h+var_110], xmm0
0x140016fdd  mov     [rbp+430h+var_F0], eax
0x140016fe3  mov     eax, 806h
0x140016fe8  movups  xmm0, cs:FWPM_CONDITION_ETHER_TYPE
0x140016fef  xor     r8d, r8d; sd
0x140016ff2  mov     [rbp+430h+var_100], r15d
0x140016ff9  mov     [rbp+430h+var_F8], r14d
0x140017000  movdqu  [rbp+430h+var_E8], xmm0
0x140017008  mov     [rbp+430h+var_D8], r15d
0x14001700f  mov     [rbp+430h+var_D0], 2
0x140017019  mov     [rbp+430h+var_C8], ax
0x140017020  call    cs:__imp_FwpmFilterAdd0
0x140017027  nop     dword ptr [rax+rax+00h]
0x14001702c  mov     ebx, eax
0x14001702e  test    eax, eax
0x140017030  jns     short loc_140017066
0x140017032  test    byte ptr cs:xmmword_1400262D0, 2
0x140017039  jz      short loc_140017050
0x14001703b  mov     edx, 1Ah
0x140017040  mov     r9d, eax
0x140017043  mov     r8, r12
0x140017046  mov     ecx, 201h
0x14001704b  call    WPP_SF_d
0x140017050  mov     rcx, [rsp+530h+var_500]; engineHandle
0x140017055  call    cs:__imp_FwpmTransactionAbort0
0x14001705c  nop     dword ptr [rax+rax+00h]
0x140017061  jmp     loc_140017138
0x140017066  mov     rcx, [rsp+530h+var_500]; engineHandle
0x14001706b  call    cs:__imp_FwpmTransactionCommit0
0x140017072  nop     dword ptr [rax+rax+00h]
0x140017077  jmp     loc_140017138
0x14001707c  mov     rdx, [rdi+30h]; id
0x140017080  test    rdx, rdx
0x140017083  jz      short loc_1400170A5
0x140017085  mov     rcx, [rsp+530h+var_500]; engineHandle
0x14001708a  call    cs:__imp_FwpmFilterDeleteById0
0x140017091  nop     dword ptr [rax+rax+00h]
0x140017096  mov     ebx, eax
0x140017098  test    eax, eax
0x14001709a  jns     short loc_1400170A1
0x14001709c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400170a1  mov     [rdi+30h], r15
0x1400170a5  mov     rdx, [rdi+38h]; id
0x1400170a9  test    rdx, rdx
0x1400170ac  jz      short loc_1400170CE
0x1400170ae  mov     rcx, [rsp+530h+var_500]; engineHandle
0x1400170b3  call    cs:__imp_FwpmFilterDeleteById0
0x1400170ba  nop     dword ptr [rax+rax+00h]
0x1400170bf  mov     ebx, eax
0x1400170c1  test    eax, eax
0x1400170c3  jns     short loc_1400170CA
0x1400170c5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400170ca  mov     [rdi+38h], r15
0x1400170ce  mov     rdx, [rdi+40h]; id
0x1400170d2  test    rdx, rdx
0x1400170d5  jz      short loc_1400170F7
0x1400170d7  mov     rcx, [rsp+530h+var_500]; engineHandle
0x1400170dc  call    cs:__imp_FwpmFilterDeleteById0
0x1400170e3  nop     dword ptr [rax+rax+00h]
0x1400170e8  mov     ebx, eax
0x1400170ea  test    eax, eax
0x1400170ec  jns     short loc_1400170F3
0x1400170ee  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400170f3  mov     [rdi+40h], r15
0x1400170f7  mov     eax, cs:Feature_CLAT_WinNAT_DropSyntheticIPv4DAD__private_featureState
0x1400170fd  test    al, 10h
  ... truncated ...
```
