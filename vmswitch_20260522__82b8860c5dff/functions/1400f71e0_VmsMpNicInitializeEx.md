# VmsMpNicInitializeEx

- ea: `0x1400f71e0`
- end: `0x1400f810e`
- name: `VmsMpNicInitializeEx`
- size: `3886`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400f5b50`

## callees

- `0x140027a64`
- `0x14002d258`
- `0x14002e45c`
- `0x14003c378`
- `0x14003e804`
- `0x14003e9e4`
- `0x140046f1c`
- `0x140052460`
- `0x14005deb8`
- `0x14006b990`
- `0x14006e0b0`
- `0x14008497c`
- `0x14008d88c`
- `0x1400f4d44`
- `0x1400f71e0`
- `0x1400f8b48`
- `0x1400f92c0`
- `0x1400fa7c0`
- `0x140142a20`
- `0x1401bbc40`
- `0x1401bbe10`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400f7e7a`
- `ntoskrnl!KeReleaseMutex` at `0x1400f7f84`
- `ntoskrnl!KeReleaseMutex` at `0x1400f7f95`
- `ntoskrnl!KeReleaseMutex` at `0x1400f800d`
- `ntoskrnl!KeReleaseMutex` at `0x1400f7e7a`
- `ntoskrnl!KeReleaseMutex` at `0x1400f7f84`
- `ntoskrnl!KeReleaseMutex` at `0x1400f7f95`
- `ntoskrnl!KeReleaseMutex` at `0x1400f800d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f73d6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f7f35`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f7fbd`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f73d6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f7f35`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f7fbd`
- `NDIS!NdisReadNetworkAddress` at `0x1400f757c`
- `NDIS!NdisReadNetworkAddress` at `0x1400f757c`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x1400f731e`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x1400f731e`
- `NDIS!NdisCloseConfiguration` at `0x1400f7a8b`
- `NDIS!NdisCloseConfiguration` at `0x1400f7a8b`
- `NDIS!NdisReadConfiguration` at `0x1400f7606`
- `NDIS!NdisReadConfiguration` at `0x1400f764a`
- `NDIS!NdisReadConfiguration` at `0x1400f768e`
- `NDIS!NdisReadConfiguration` at `0x1400f76d2`
- `NDIS!NdisReadConfiguration` at `0x1400f7716`
- `NDIS!NdisReadConfiguration` at `0x1400f775a`
- `NDIS!NdisReadConfiguration` at `0x1400f779e`
- `NDIS!NdisReadConfiguration` at `0x1400f77e2`
- `NDIS!NdisReadConfiguration` at `0x1400f7837`
- `NDIS!NdisReadConfiguration` at `0x1400f7895`
- `NDIS!NdisReadConfiguration` at `0x1400f7964`
- `NDIS!NdisReadConfiguration` at `0x1400f79d4`
- `NDIS!NdisReadConfiguration` at `0x1400f7a18`
- `NDIS!NdisReadConfiguration` at `0x1400f7a5c`
- `NDIS!NdisReadConfiguration` at `0x1400f7606`
- `NDIS!NdisReadConfiguration` at `0x1400f764a`
- `NDIS!NdisReadConfiguration` at `0x1400f768e`
- `NDIS!NdisReadConfiguration` at `0x1400f76d2`
- `NDIS!NdisReadConfiguration` at `0x1400f7716`
- `NDIS!NdisReadConfiguration` at `0x1400f775a`
- `NDIS!NdisReadConfiguration` at `0x1400f779e`
- `NDIS!NdisReadConfiguration` at `0x1400f77e2`
- `NDIS!NdisReadConfiguration` at `0x1400f7837`
- `NDIS!NdisReadConfiguration` at `0x1400f7895`
- `NDIS!NdisReadConfiguration` at `0x1400f7964`
- `NDIS!NdisReadConfiguration` at `0x1400f79d4`
- `NDIS!NdisReadConfiguration` at `0x1400f7a18`
- `NDIS!NdisReadConfiguration` at `0x1400f7a5c`
- `NDIS!NdisOpenConfigurationEx` at `0x1400f7550`
- `NDIS!NdisOpenConfigurationEx` at `0x1400f7550`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x1400f730c`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x1400f730c`

## pseudocode

```c
__int64 __fastcall VmsMpNicInitializeEx(void *a1, __int64 a2, __int64 a3)
{
  char v4; // r14
  __int64 v6; // rbx
  int v7; // edx
  int v8; // r8d
  __int64 v9; // rdi
  char v10; // si
  unsigned int v11; // eax
  int v12; // edx
  int v13; // edx
  int v14; // r8d
  int v15; // edx
  int v16; // r8d
  int v17; // eax
  int v18; // edx
  int v19; // ecx
  __int128 v20; // xmm0
  bool v21; // r14
  __int128 v22; // xmm1
  __int16 v23; // ax
  __int128 v24; // xmm0
  __int16 v25; // ax
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  _WORD *v29; // rcx
  ULONG IntegerData; // ecx
  char v31; // r14
  bool v32; // zf
  int v33; // edx
  int v34; // r8d
  char v35; // si
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // edx
  unsigned __int8 v40; // al
  unsigned __int8 v41; // al
  int v42; // eax
  int v43; // edx
  int v44; // eax
  int v45; // edx
  int v46; // edx
  _DWORD *v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rax
  __int64 v51; // rdi
  int v52; // edx
  int Status; // [rsp+50h] [rbp-B0h] BYREF
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+58h] [rbp-A8h] BYREF
  PVOID ConfigurationHandle; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int NetworkAddressLength; // [rsp+6Ch] [rbp-94h] BYREF
  PVOID NetworkAddress; // [rsp+70h] [rbp-90h] BYREF
  __int64 v59; // [rsp+78h] [rbp-88h]
  __int128 v60; // [rsp+80h] [rbp-80h] BYREF
  __m256i v61; // [rsp+90h] [rbp-70h] BYREF
  __int128 v62; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v63; // [rsp+C0h] [rbp-40h]
  __int64 v64; // [rsp+D0h] [rbp-30h]
  struct _NDIS_CONFIGURATION_OBJECT ConfigObject; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v66; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v67; // [rsp+100h] [rbp+0h]
  __int128 v68; // [rsp+110h] [rbp+10h]
  _BYTE *v69; // [rsp+120h] [rbp+20h]
  _QWORD v70[28]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v71; // [rsp+210h] [rbp+110h] BYREF
  int v72; // [rsp+220h] [rbp+120h]
  _BYTE v73[112]; // [rsp+230h] [rbp+130h] BYREF

  v59 = a2;
  Status = -1073741823;
  ConfigurationHandle = 0;
  v4 = a2;
  NetworkAddress = 0;
  NetworkAddressLength = 0;
  memset(&v61, 0, 28);
  ParameterValue = 0;
  v72 = 0;
  v6 = 0;
  memset(&ConfigObject, 0, sizeof(ConfigObject));
  v71 = 0;
  memset(v70, 0, sizeof(v70));
  v62 = 0;
  LODWORD(v64) = 0;
  v63 = 0;
  v69 = 0;
  v60 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  memset(v73, 0, 0x68u);
  if ( !(unsigned __int8)VmsUtilVerifyNdisObjectHeader(a3) )
  {
    v9 = 0;
    Status = 65539;
    v10 = 1;
    goto LABEL_77;
  }
  v9 = *(_QWORD *)(a3 + 16);
  if ( !v9 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v7,
      19,
      52,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      (__int64)"objNic");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v11 = ConvertInterfaceLuidToGuid((const NET_LUID *)(a3 + 40), (GUID *)(v9 + 1816));
  if ( v11 )
  {
    Status = NdisConvertNtStatusToNdisStatus(v11);
    v10 = 7;
    WPP_RECORDER_SF_Id(
      VmsIfrNicLog,
      v13,
      v14,
      53,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      *(_QWORD *)(a3 + 40),
      Status);
    goto LABEL_77;
  }
  v6 = *(_QWORD *)(v9 + 3312);
  if ( !v6 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v12,
      19,
      54,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      (__int64)"mpExt");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( BYTE1(WPP_GLOBAL_Control->Timer) > 4u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_I(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      7,
      55,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      v9);
  KeWaitForSingleObject((PVOID)(v6 + 40), Executive, 0, 0, 0);
  if ( *(_DWORD *)(v6 + 32) )
  {
    v10 = 2;
    Status = -1073741823;
    WPP_RECORDER_SF_Ld(
      VmsIfrNicLog,
      v15,
      v16,
      56,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      *(_DWORD *)(v6 + 32),
      1);
  }
  else
  {
    *(_QWORD *)(v6 + 24) = a1;
    *(_DWORD *)(v6 + 936) = *(_DWORD *)(a3 + 32);
    v61.m256i_i64[0] = 2097566;
    v61.m256i_i64[1] = v9;
    *(_OWORD *)&v61.m256i_u64[2] = 0x20u;
    v17 = ((__int64 (__fastcall *)(void *, __m256i *))qword_1401F9528)(a1, &v61);
    Status = v17;
    if ( v17 )
    {
      v10 = 3;
      LOBYTE(v18) = 2;
      WPP_RECORDER_SF_qqd(
        VmsIfrNicLog,
        v18,
        20,
        57,
        (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
        (char)a1,
        (char)&v61,
        v17);
    }
    else
    {
      v19 = *(_DWORD *)(v9 + 2104);
      v20 = *(_OWORD *)(v9 + 3364);
      *(_DWORD *)(v9 + 3336) = v19;
      v21 = 0;
      v22 = *(_OWORD *)(v9 + 3380);
      *(_WORD *)(v9 + 3340) = *(_WORD *)(v9 + 2108);
      *(_DWORD *)(v9 + 1838) = v19;
      v23 = *(_WORD *)(v9 + 2108);
      *(_OWORD *)(v9 + 3460) = v20;
      *(_WORD *)(v9 + 1842) = v23;
      v24 = *(_OWORD *)(v9 + 3396);
      v25 = *(_WORD *)(v9 + 2108);
      *(_OWORD *)(v9 + 3476) = v22;
      *(_DWORD *)(v9 + 3342) = v19;
      v26 = *(_OWORD *)(v9 + 3412);
      *(_WORD *)(v9 + 3346) = v25;
      *(_OWORD *)(v9 + 3492) = v24;
      v27 = *(_OWORD *)(v9 + 3428);
      *(_OWORD *)(v9 + 3508) = v26;
      v28 = *(_OWORD *)(v9 + 3444);
      *(_OWORD *)(v9 + 3524) = v27;
      *(_OWORD *)(v9 + 3540) = v28;
      ConfigObject.Header = (NDIS_OBJECT_HEADER)1573289;
      ConfigObject.NdisHandle = a1;
      ConfigObject.Flags = 0;
      Status = NdisOpenConfigurationEx(&ConfigObject, &ConfigurationHandle);
      if ( !Status )
      {
        NdisReadNetworkAddress(&Status, &NetworkAddress, &NetworkAddressLength, ConfigurationHandle);
        if ( !Status && NetworkAddressLength == 6 )
        {
          v29 = NetworkAddress;
          if ( (*(_BYTE *)NetworkAddress & 1) == 0 && (*(_DWORD *)NetworkAddress || *((_WORD *)NetworkAddress + 2)) )
          {
            *(_DWORD *)(v9 + 3336) = *(_DWORD *)NetworkAddress;
            *(_WORD *)(v9 + 3340) = v29[2];
            *(_DWORD *)(v9 + 1838) = *(_DWORD *)v29;
            *(_WORD *)(v9 + 1842) = v29[2];
            *(_DWORD *)(v9 + 3342) = *(_DWORD *)NetworkAddress;
            *(_WORD *)(v9 + 3346) = *((_WORD *)NetworkAddress + 2);
          }
        }
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonIp4IpChecksum,
          NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp4IpChecksum, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonIp4TcpChecksum,
          NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp4TcpChecksum, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonIp6TcpChecksum,
          NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp6TcpChecksum, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonIp4UdpChecksum,
          NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp4UdpChecksum, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonIp6UdpChecksum,
          NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp6UdpChecksum, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonIp4TcpLsoV2,
          NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp4TcpLsoV2, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonIp6TcpLsoV2,
          NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp6TcpLsoV2, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonJumboPacket,
          NdisParameterInteger);
        if ( Status
          || (IntegerData = ParameterValue->ParameterData.IntegerData, IntegerData < 0x5EA)
          || IntegerData > VmsVmMaximumMTU )
        {
          IntegerData = 1514;
        }
        *(_DWORD *)(v9 + 3356) = IntegerData - *(_DWORD *)(v9 + 4064);
        NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &VmsMiniCommonIp4Rsc, NdisParameterInteger);
        v31 = *(_BYTE *)(v9 + 3952);
        if ( !Status )
        {
          v32 = ParameterValue->ParameterData.IntegerData == 0;
          *(_BYTE *)(v9 + 3954) = 0;
          *(_BYTE *)(v9 + 3952) = !v32;
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp4Rsc, 0);
        }
        NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &VmsMiniCommonIp6Rsc, NdisParameterInteger);
        v35 = *(_BYTE *)(v9 + 3953);
        if ( !Status )
        {
          v32 = ParameterValue->ParameterData.IntegerData == 0;
          *(_BYTE *)(v9 + 3955) = 0;
          *(_BYTE *)(v9 + 3953) = !v32;
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp6Rsc, 0);
        }
        if ( (Microsoft_Windows_Hyper_V_VmSwitchEnableBits & 2) != 0 )
          McTemplateK0zzqqqqq_EtwWriteTransfer(
            *(unsigned __int8 *)(v9 + 3954),
            v33,
            v34,
            *(_QWORD *)(v9 + 80),
            *(_QWORD *)(v9 + 624),
            v31,
            v35,
            *(_BYTE *)(v9 + 3954),
            *(_BYTE *)(v9 + 3955),
            4);
        if ( *(_BYTE *)(v9 + 3952) != *(_BYTE *)(v9 + 3953) )
          VmsEtwTraceNicName((unsigned int)VM_NIC_RSC_SUBOPTIMAL_CONFIG_WARNING, v33, v34, v9 + 72, v9 + 616);
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonRssEnabled,
          NdisParameterInteger);
        if ( Status )
        {
          v21 = 0;
        }
        else
        {
          v32 = ParameterValue->ParameterData.IntegerData == 1;
          v72 = 128;
          v21 = v32;
          *(_QWORD *)&v71 = 0x30100120288LL;
          *((_QWORD *)&v71 + 1) = 0x1000000001LL;
        }
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonNetworkDirect,
          NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonNetworkDirect, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &VmsMiniCommonIp4Uso, NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp4Uso, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &VmsMiniCommonIp6Uso, NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp6Uso, ParameterValue->ParameterData.IntegerData);
        NdisCloseConfiguration(ConfigurationHandle);
      }
      memset(v70, 0, sizeof(v70));
      LODWORD(v70[0]) = 14680479;
      v70[1] = 0;
      LODWORD(v70[2]) = *(_DWORD *)(v9 + 3356) - 14;
      v70[3] = 10000000000LL;
      v70[4] = 10000000000LL;
      v70[5] = 10000000000LL;
      v70[6] = 10000000000LL;
      v70[7] = (unsigned int)VmsOmNicGetMediaConnectState(v9);
      v36 = *(_DWORD *)(v9 + 3356) - 14;
      v70[9] = 0;
      LODWORD(v70[8]) = v36;
      v10 = 8;
      v70[10] = 0x2F00000008LL;
      v37 = 8;
      LODWORD(v70[11]) = 64;
      WORD2(v70[11]) = 6;
      if ( *(_BYTE *)(v9 + 3556) == 1 )
        v37 = 584;
      LODWORD(v70[10]) = v37;
      *(_DWORD *)((char *)&v70[15] + 6) = *(_DWORD *)(v9 + 3336);
      WORD1(v70[16]) = *(_WORD *)(v9 + 3340);
      *(_DWORD *)((char *)&v70[11] + 6) = *(_DWORD *)(v9 + 2104);
      WORD1(v70[12]) = *(_WORD *)(v9 + 2108);
      WORD2(v70[22]) = 6;
      v70[20] = (unsigned __int64)&v71 & -(__int64)v21;
      v70[21] = 2;
      v70[25] = VmsMpCommonNdis63VspOids;
      LODWORD(v70[22]) = 1;
      BYTE6(v70[22]) = 0;
      v70[23] = 1652032;
      v70[24] = 0x2000000000LL;
      LODWORD(v70[26]) = 248;
      v38 = ((__int64 (__fastcall *)(void *, _QWORD *))qword_1401F9528)(a1, v70);
      Status = v38;
      if ( v38 )
      {
        v10 = 4;
        LOBYTE(v39) = 2;
        WPP_RECORDER_SF_qqd(
          VmsIfrNicLog,
          v39,
          20,
          58,
          (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
          (char)a1,
          (char)v70,
          v38);
      }
      else
      {
        *(_QWORD *)(v6 + 944) = 0;
        *(_QWORD *)(v6 + 952) = 0;
        *(_QWORD *)(v6 + 928) = 10000000000LL;
        v62 = 0;
        v64 = 0;
        v63 = 0;
        LODWORD(v62) = 2621856;
        *(_DWORD *)(v6 + 708) = *(_DWORD *)(v9 + 3460);
        v40 = *(_BYTE *)(v6 + 709);
        *(_OWORD *)(v6 + 712) = *(_OWORD *)(v9 + 3464);
        *(_OWORD *)(v6 + 728) = *(_OWORD *)(v9 + 3480);
        *(_OWORD *)(v6 + 788) = *(_OWORD *)(v9 + 3496);
        *(_OWORD *)(v6 + 800) = *(_OWORD *)(v9 + 3508);
        if ( v40 >= 2u )
        {
          *(_OWORD *)(v6 + 820) = *(_OWORD *)(v9 + 3992);
          *(_OWORD *)(v6 + 836) = *(_OWORD *)(v9 + 4008);
        }
        if ( v40 >= 3u )
          *(_WORD *)(v6 + 852) = *(_WORD *)(v9 + 3954);
        *((_QWORD *)&v62 + 1) = v6 + 708;
        *(_DWORD *)(v6 + 488) = *(_DWORD *)(v9 + 3364);
        v41 = *(_BYTE *)(v6 + 489);
        *(_OWORD *)(v6 + 492) = *(_OWORD *)(v9 + 3368);
        *(_OWORD *)(v6 + 508) = *(_OWORD *)(v9 + 3384);
        *(_OWORD *)(v6 + 568) = *(_OWORD *)(v9 + 3400);
        *(_OWORD *)(v6 + 580) = *(_OWORD *)(v9 + 3412);
        if ( v41 >= 2u )
        {
          *(_OWORD *)(v6 + 600) = *(_OWORD *)(v9 + 3960);
          *(_OWORD *)(v6 + 616) = *(_OWORD *)(v9 + 3976);
        }
        if ( v41 >= 3u )
          *(_WORD *)(v6 + 632) = *(_WORD *)(v9 + 3952);
        *(_QWORD *)&v63 = v6 + 488;
        v42 = ((__int64 (__fastcall *)(void *, __int128 *))qword_1401F9528)(a1, &v62);
        Status = v42;
        if ( v42 )
        {
          v10 = 5;
          LOBYTE(v43) = 2;
          WPP_RECORDER_SF_qqd(
            VmsIfrNicLog,
            v43,
            20,
            59,
            (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
            (char)a1,
            (char)&v62,
            v42);
        }
        else
        {
          v66 = 0;
          LODWORD(v66) = 3670400;
          v67 = 0;
          v68 = 0;
          memset(v73, 0, 0x68u);
          v69 = v73;
          *(_QWORD *)&v60 = 1049011;
          *((_QWORD *)&v60 + 1) = &v66;
          v44 = ((__int64 (__fastcall *)(_QWORD, __int128 *))qword_1401F9528)(*(_QWORD *)(v6 + 24), &v60);
          Status = v44;
          if ( !v44 )
          {
            *(_DWORD *)(v9 + 4880) |= 2u;
            *(_DWORD *)(v9 + 4848) = 14;
            *(_DWORD *)(v9 + 4764) = 1;
            *(_BYTE *)(v9 + 4852) = 0;
            *(_DWORD *)(v9 + 4856) = 0;
            *(_BYTE *)(v9 + 4864) = 0;
            v10 = 0;
            *(_DWORD *)(v6 + 32) = 1;
            *(_BYTE *)(v6 + 941) = 1;
            KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
            if ( *(_DWORD *)(v9 + 1880) == 1 )
            {
              v47 = *(_DWORD **)(v9 + 1888);
              if ( (unsigned int)(v47[1068] - 2) <= 1 && v47[1284] && v47[1285] )
                VmsMpNicPvtUpdateNdisStack(v9, 0);
            }
            KeReleaseMutex(&VmsOmIoctlMutex, 0);
            KeReleaseMutex((PRKMUTEX)(v6 + 40), 0);
            VmsMpNicPvtPinMacAddress(v9);
            KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
            if ( *(_DWORD *)(v9 + 1880) == 1 )
            {
              v48 = *(_QWORD *)(v9 + 1888);
              if ( v48 )
              {
                v49 = *(_QWORD *)(v48 + 4264);
                if ( v49 )
                {
                  if ( *(_DWORD *)(v49 + 4764) == 3 && *(_BYTE *)(v9 + 4760) )
                    VmsNdkRequestRdma(v9);
                }
              }
            }
            KeReleaseMutex(&VmsOmIoctlMutex, 0);
            if ( BYTE1(WPP_GLOBAL_Control->Timer) > 4u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
              WPP_RECORDER_SF_id(
                WPP_GLOBAL_Control->DeviceExtension,
                0,
                7,
                62,
                (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
                v6,
                Status);
            goto LABEL_76;
          }
          LOBYTE(v45) = 2;
          WPP_RECORDER_SF_qqd(
            VmsIfrNicLog,
            v45,
            20,
            60,
            (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
            *(_QWORD *)(v6 + 24),
            (char)&v60,
            v44);
        }
      }
    }
  }
  KeReleaseMutex((PRKMUTEX)(v6 + 40), 0);
LABEL_76:
  v4 = v59;
LABEL_77:
  if ( Status )
  {
    if ( v6 )
    {
      *(_QWORD *)(v6 + 24) = 0;
      *(_DWORD *)(v6 + 32) = 2;
    }
    if ( v9 )
    {
      v50 = v9 + 72;
      v51 = v9 + 616;
    }
    else
    {
      v50 = 0;
      v51 = 0;
    }
    VmsEtwTraceSwitchFailure(&VM_FAILED_TO_INITIALIZE_MINIPORT_NIC, v10, v50, v51);
    LOBYTE(v52) = 2;
    WPP_RECORDER_SF_qqqd(
      VmsIfrNicLog,
      v52,
      20,
      64,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      (char)a1,
      v4,
      a3,
      Status);
  }
  else
  {
    VmsEtwTraceNicName((unsigned int)VM_MINIPORT_SUCCESSFULLY_INITIALIZED, v7, v8, v9 + 72, v9 + 616);
    WPP_RECORDER_SF_qZ(VmsIfrNicLog, v46, 1, 63, (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids, v9, v9 + 616);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400f71e0  mov     [rsp-8+arg_18], rbx
0x1400f71e5  push    rbp
0x1400f71e6  push    rsi
0x1400f71e7  push    rdi
0x1400f71e8  push    r12
0x1400f71ea  push    r13
0x1400f71ec  push    r14
0x1400f71ee  push    r15
0x1400f71f0  lea     rbp, [rsp-1B0h]
0x1400f71f8  sub     rsp, 2B0h
0x1400f71ff  mov     rax, cs:__security_cookie
0x1400f7206  xor     rax, rsp
0x1400f7209  mov     [rbp+1E0h+var_40], rax
0x1400f7210  xorps   xmm0, xmm0
0x1400f7213  mov     [rsp+2E0h+var_268], rdx
0x1400f7218  xor     esi, esi
0x1400f721a  mov     [rsp+2E0h+Status], 0C0000001h
0x1400f7222  xor     eax, eax
0x1400f7224  mov     [rsp+2E0h+ConfigurationHandle], rsi
0x1400f7229  mov     r13, r8
0x1400f722c  mov     qword ptr [rbp+1E0h+ConfigObject.Flags], rax
0x1400f7230  mov     r14, rdx
0x1400f7233  mov     [rsp+2E0h+NetworkAddress], rsi
0x1400f7238  mov     r15, rcx
0x1400f723b  mov     [rsp+2E0h+NetworkAddressLength], esi
0x1400f723f  movups  [rbp+1E0h+var_250], xmm0
0x1400f7243  xor     edx, edx; Val
0x1400f7245  mov     [rsp+2E0h+ParameterValue], rsi
0x1400f724a  mov     r8d, 0E0h; Size
0x1400f7250  mov     [rbp+1E0h+var_C0], eax
0x1400f7256  lea     rcx, [rbp+1E0h+var_1B0]; void *
0x1400f725a  mov     ebx, esi
0x1400f725c  movups  [rbp+1E0h+var_250+0Ch], xmm0
0x1400f7260  movups  xmmword ptr [rbp+1E0h+ConfigObject.Header.Type], xmm0
0x1400f7264  movups  [rbp+1E0h+var_D0], xmm0
0x1400f726b  call    memset
0x1400f7270  xorps   xmm0, xmm0
0x1400f7273  lea     r8d, [rsi+68h]; Size
0x1400f7277  xorps   xmm1, xmm1
0x1400f727a  lea     rcx, [rbp+1E0h+var_B0]; void *
0x1400f7281  xor     eax, eax
0x1400f7283  xor     edx, edx; Val
0x1400f7285  movups  [rbp+1E0h+var_230], xmm0
0x1400f7289  mov     dword ptr [rbp+1E0h+var_210], eax
0x1400f728c  movups  [rbp+1E0h+var_220], xmm0
0x1400f7290  mov     [rbp+1E0h+var_1C0], rax
0x1400f7294  movups  [rbp+1E0h+var_260], xmm0
0x1400f7298  movups  [rbp+1E0h+var_1F0], xmm1
0x1400f729c  movups  [rbp+1E0h+var_1E0], xmm1
0x1400f72a0  movups  [rbp+1E0h+var_1D0], xmm1
0x1400f72a4  call    memset
0x1400f72a9  mov     rcx, r13
0x1400f72ac  call    VmsUtilVerifyNdisObjectHeader
0x1400f72b1  lea     r12, WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids
0x1400f72b8  test    al, al
0x1400f72ba  jnz     short loc_1400F72CE
0x1400f72bc  mov     edi, esi
0x1400f72be  mov     [rsp+2E0h+Status], 10003h
0x1400f72c6  lea     esi, [rdi+1]
0x1400f72c9  jmp     loc_1400F7E92
0x1400f72ce  mov     rdi, [r13+10h]
0x1400f72d2  test    rdi, rdi
0x1400f72d5  jnz     short loc_1400F7301
0x1400f72d7  mov     rcx, cs:VmsIfrLog
0x1400f72de  lea     rax, aObjnic; "objNic"
0x1400f72e5  mov     [rsp+2E0h+var_2B8], rax
0x1400f72ea  lea     r9d, [rdi+34h]
0x1400f72ee  lea     r8d, [rdi+13h]
0x1400f72f2  mov     [rsp+2E0h+Timeout], r12
0x1400f72f7  call    WPP_RECORDER_SF_s
0x1400f72fc  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "objNic")
0x1400f7301  lea     rdx, [rdi+718h]; InterfaceGuid
0x1400f7308  lea     rcx, [r13+28h]; InterfaceLuid
0x1400f730c  call    cs:__imp_ConvertInterfaceLuidToGuid
0x1400f7313  nop     dword ptr [rax+rax+00h]
0x1400f7318  test    eax, eax
0x1400f731a  jz      short loc_1400F735A
0x1400f731c  mov     ecx, eax
0x1400f731e  call    cs:__imp_NdisConvertNtStatusToNdisStatus
0x1400f7325  nop     dword ptr [rax+rax+00h]
0x1400f732a  mov     [rsp+2E0h+Status], eax
0x1400f732e  mov     esi, 7
0x1400f7333  mov     rcx, cs:VmsIfrNicLog
0x1400f733a  lea     r9d, [rsi+2Eh]
0x1400f733e  mov     dword ptr [rsp+2E0h+var_2B0], eax
0x1400f7342  mov     rax, [r13+28h]
0x1400f7346  mov     [rsp+2E0h+var_2B8], rax
0x1400f734b  mov     [rsp+2E0h+Timeout], r12
0x1400f7350  call    WPP_RECORDER_SF_Id
0x1400f7355  jmp     loc_1400F7E92
0x1400f735a  mov     rbx, [rdi+0CF0h]
0x1400f7361  test    rbx, rbx
0x1400f7364  jnz     short loc_1400F7390
0x1400f7366  mov     rcx, cs:VmsIfrLog
0x1400f736d  lea     rax, aMpext; "mpExt"
0x1400f7374  mov     [rsp+2E0h+var_2B8], rax
0x1400f7379  lea     r9d, [rbx+36h]
0x1400f737d  lea     r8d, [rbx+13h]
0x1400f7381  mov     [rsp+2E0h+Timeout], r12
0x1400f7386  call    WPP_RECORDER_SF_s
0x1400f738b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "mpExt")
0x1400f7390  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f7397  cmp     byte ptr [rcx+29h], 4
0x1400f739b  ja      short loc_1400F73A3
0x1400f739d  cmp     [rcx+48h], si
0x1400f73a1  jz      short loc_1400F73C2
0x1400f73a3  mov     rcx, [rcx+40h]
0x1400f73a7  mov     r9d, 37h ; '7'
0x1400f73ad  mov     [rsp+2E0h+var_2B8], rdi
0x1400f73b2  xor     edx, edx
0x1400f73b4  mov     [rsp+2E0h+Timeout], r12
0x1400f73b9  lea     r8d, [r9-30h]
0x1400f73bd  call    WPP_RECORDER_SF_I
0x1400f73c2  lea     r12, [rbx+28h]
0x1400f73c6  mov     [rsp+2E0h+Timeout], rsi; Timeout
0x1400f73cb  mov     rcx, r12; Object
0x1400f73ce  xor     r9d, r9d; Alertable
0x1400f73d1  xor     r8d, r8d; WaitMode
0x1400f73d4  xor     edx, edx; WaitReason
0x1400f73d6  call    cs:__imp_KeWaitForSingleObject
0x1400f73dd  nop     dword ptr [rax+rax+00h]
0x1400f73e2  cmp     [rbx+20h], esi
0x1400f73e5  jz      short loc_1400F7421
0x1400f73e7  mov     ecx, 0C0000001h
0x1400f73ec  mov     esi, 2
0x1400f73f1  mov     [rsp+2E0h+Status], ecx
0x1400f73f5  mov     eax, [rbx+20h]
0x1400f73f8  lea     r9d, [rsi+36h]
0x1400f73fc  mov     dword ptr [rsp+2E0h+var_2B0], ecx
0x1400f7400  mov     rcx, cs:VmsIfrNicLog
0x1400f7407  mov     dword ptr [rsp+2E0h+var_2B8], eax
0x1400f740b  lea     rax, WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids
0x1400f7412  mov     [rsp+2E0h+Timeout], rax
0x1400f7417  call    WPP_RECORDER_SF_Ld
0x1400f741c  jmp     loc_1400F7E75
0x1400f7421  mov     [rbx+18h], r15
0x1400f7425  lea     rdx, [rbp+1E0h+var_250]
0x1400f7429  mov     eax, [r13+20h]
0x1400f742d  mov     rcx, r15
0x1400f7430  mov     [rbx+3A8h], eax
0x1400f7436  mov     rax, cs:qword_1401F9528
0x1400f743d  mov     qword ptr [rbp+1E0h+var_250], 20019Eh
0x1400f7445  mov     [rbp+1E0h+var_238], rsi
0x1400f7449  mov     qword ptr [rbp+1E0h+var_250+8], rdi
0x1400f744d  mov     [rbp+1E0h+var_240], 20h ; ' '
0x1400f7455  call    _guard_dispatch_icall
0x1400f745a  mov     [rsp+2E0h+Status], eax
0x1400f745e  test    eax, eax
0x1400f7460  jz      short loc_1400F74A0
0x1400f7462  mov     esi, 3
0x1400f7467  mov     rcx, cs:VmsIfrNicLog
0x1400f746e  lea     r9d, [rsi+36h]
0x1400f7472  mov     dword ptr [rsp+2E0h+var_2A8], eax
0x1400f7476  lea     r8d, [rsi+11h]
0x1400f747a  lea     rax, [rbp+1E0h+var_250]
0x1400f747e  mov     dl, 2
0x1400f7480  mov     [rsp+2E0h+var_2B0], rax
0x1400f7485  lea     rax, WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids
0x1400f748c  mov     [rsp+2E0h+var_2B8], r15
0x1400f7491  mov     [rsp+2E0h+Timeout], rax
0x1400f7496  call    WPP_RECORDER_SF_qqd
0x1400f749b  jmp     loc_1400F7E75
0x1400f74a0  mov     ecx, [rdi+838h]
0x1400f74a6  lea     rdx, [rsp+2E0h+ConfigurationHandle]; ConfigurationHandle
0x1400f74ab  movups  xmm0, xmmword ptr [rdi+0D24h]
0x1400f74b2  mov     [rdi+0D08h], ecx
0x1400f74b8  mov     r14b, sil
0x1400f74bb  movzx   eax, word ptr [rdi+83Ch]
0x1400f74c2  movups  xmm1, xmmword ptr [rdi+0D34h]
0x1400f74c9  mov     [rdi+0D0Ch], ax
0x1400f74d0  mov     [rdi+72Eh], ecx
0x1400f74d6  movzx   eax, word ptr [rdi+83Ch]
0x1400f74dd  movups  xmmword ptr [rdi+0D84h], xmm0
0x1400f74e4  mov     [rdi+732h], ax
0x1400f74eb  movups  xmm0, xmmword ptr [rdi+0D44h]
0x1400f74f2  movzx   eax, word ptr [rdi+83Ch]
0x1400f74f9  movups  xmmword ptr [rdi+0D94h], xmm1
0x1400f7500  mov     [rdi+0D0Eh], ecx
0x1400f7506  lea     rcx, [rbp+1E0h+ConfigObject]; ConfigObject
0x1400f750a  movups  xmm1, xmmword ptr [rdi+0D54h]
0x1400f7511  mov     [rdi+0D12h], ax
0x1400f7518  movups  xmmword ptr [rdi+0DA4h], xmm0
0x1400f751f  movups  xmm0, xmmword ptr [rdi+0D64h]
0x1400f7526  movups  xmmword ptr [rdi+0DB4h], xmm1
0x1400f752d  movups  xmm1, xmmword ptr [rdi+0D74h]
0x1400f7534  movups  xmmword ptr [rdi+0DC4h], xmm0
0x1400f753b  movups  xmmword ptr [rdi+0DD4h], xmm1
0x1400f7542  mov     dword ptr [rbp+1E0h+ConfigObject.Header.Type], 1801A9h
0x1400f7549  mov     [rbp+1E0h+ConfigObject.NdisHandle], r15
0x1400f754d  mov     [rbp+1E0h+ConfigObject.Flags], esi
0x1400f7550  call    cs:__imp_NdisOpenConfigurationEx
0x1400f7557  nop     dword ptr [rax+rax+00h]
0x1400f755c  mov     [rsp+2E0h+Status], eax
0x1400f7560  test    eax, eax
0x1400f7562  jnz     loc_1400F7A97
0x1400f7568  mov     r9, [rsp+2E0h+ConfigurationHandle]; ConfigurationHandle
0x1400f756d  lea     r8, [rsp+2E0h+NetworkAddressLength]; NetworkAddressLength
0x1400f7572  lea     rdx, [rsp+2E0h+NetworkAddress]; NetworkAddress
0x1400f7577  lea     rcx, [rsp+2E0h+Status]; Status
0x1400f757c  call    cs:__imp_NdisReadNetworkAddress
0x1400f7583  nop     dword ptr [rax+rax+00h]
0x1400f7588  cmp     [rsp+2E0h+Status], esi
0x1400f758c  jnz     short loc_1400F75EC
0x1400f758e  cmp     [rsp+2E0h+NetworkAddressLength], 6
0x1400f7593  jnz     short loc_1400F75EC
0x1400f7595  mov     rcx, [rsp+2E0h+NetworkAddress]
0x1400f759a  test    byte ptr [rcx], 1
0x1400f759d  jnz     short loc_1400F75EC
0x1400f759f  cmp     [rcx], esi
0x1400f75a1  jnz     short loc_1400F75A9
0x1400f75a3  cmp     [rcx+4], si
0x1400f75a7  jz      short loc_1400F75EC
0x1400f75a9  mov     eax, [rcx]
0x1400f75ab  mov     [rdi+0D08h], eax
0x1400f75b1  movzx   eax, word ptr [rcx+4]
0x1400f75b5  mov     [rdi+0D0Ch], ax
0x1400f75bc  mov     eax, [rcx]
0x1400f75be  mov     [rdi+72Eh], eax
0x1400f75c4  movzx   eax, word ptr [rcx+4]
0x1400f75c8  mov     [rdi+732h], ax
0x1400f75cf  mov     rax, [rsp+2E0h+NetworkAddress]
0x1400f75d4  mov     ecx, [rax]
0x1400f75d6  mov     [rdi+0D0Eh], ecx
0x1400f75dc  mov     rax, [rsp+2E0h+NetworkAddress]
0x1400f75e1  movzx   ecx, word ptr [rax+4]
0x1400f75e5  mov     [rdi+0D12h], cx
0x1400f75ec  mov     r8, [rsp+2E0h+ConfigurationHandle]; ConfigurationHandle
0x1400f75f1  lea     r9, VmsMiniCommonIp4IpChecksum; Keyword
0x1400f75f8  lea     rdx, [rsp+2E0h+ParameterValue]; ParameterValue
0x1400f75fd  mov     dword ptr [rsp+2E0h+Timeout], esi; ParameterType
0x1400f7601  lea     rcx, [rsp+2E0h+Status]; Status
0x1400f7606  call    cs:__imp_NdisReadConfiguration
0x1400f760d  nop     dword ptr [rax+rax+00h]
0x1400f7612  cmp     [rsp+2E0h+Status], esi
0x1400f7616  jnz     short loc_1400F7630
0x1400f7618  mov     r8, [rsp+2E0h+ParameterValue]
0x1400f761d  lea     rdx, VmsMiniCommonIp4IpChecksum
0x1400f7624  mov     rcx, rdi
0x1400f7627  mov     r8d, [r8+8]
0x1400f762b  call    VmsMpCommonSetOffload
0x1400f7630  mov     r8, [rsp+2E0h+ConfigurationHandle]; ConfigurationHandle
0x1400f7635  lea     r9, VmsMiniCommonIp4TcpChecksum; Keyword
0x1400f763c  lea     rdx, [rsp+2E0h+ParameterValue]; ParameterValue
0x1400f7641  mov     dword ptr [rsp+2E0h+Timeout], esi; ParameterType
0x1400f7645  lea     rcx, [rsp+2E0h+Status]; Status
0x1400f764a  call    cs:__imp_NdisReadConfiguration
0x1400f7651  nop     dword ptr [rax+rax+00h]
0x1400f7656  cmp     [rsp+2E0h+Status], esi
0x1400f765a  jnz     short loc_1400F7674
0x1400f765c  mov     r8, [rsp+2E0h+ParameterValue]
0x1400f7661  lea     rdx, VmsMiniCommonIp4TcpChecksum
0x1400f7668  mov     rcx, rdi
0x1400f766b  mov     r8d, [r8+8]
0x1400f766f  call    VmsMpCommonSetOffload
0x1400f7674  mov     r8, [rsp+2E0h+ConfigurationHandle]; ConfigurationHandle
0x1400f7679  lea     r9, VmsMiniCommonIp6TcpChecksum; Keyword
0x1400f7680  lea     rdx, [rsp+2E0h+ParameterValue]; ParameterValue
0x1400f7685  mov     dword ptr [rsp+2E0h+Timeout], esi; ParameterType
0x1400f7689  lea     rcx, [rsp+2E0h+Status]; Status
0x1400f768e  call    cs:__imp_NdisReadConfiguration
0x1400f7695  nop     dword ptr [rax+rax+00h]
0x1400f769a  cmp     [rsp+2E0h+Status], esi
0x1400f769e  jnz     short loc_1400F76B8
0x1400f76a0  mov     r8, [rsp+2E0h+ParameterValue]
0x1400f76a5  lea     rdx, VmsMiniCommonIp6TcpChecksum
0x1400f76ac  mov     rcx, rdi
0x1400f76af  mov     r8d, [r8+8]
0x1400f76b3  call    VmsMpCommonSetOffload
0x1400f76b8  mov     r8, [rsp+2E0h+ConfigurationHandle]; ConfigurationHandle
0x1400f76bd  lea     r9, VmsMiniCommonIp4UdpChecksum; Keyword
0x1400f76c4  lea     rdx, [rsp+2E0h+ParameterValue]; ParameterValue
0x1400f76c9  mov     dword ptr [rsp+2E0h+Timeout], esi; ParameterType
0x1400f76cd  lea     rcx, [rsp+2E0h+Status]; Status
0x1400f76d2  call    cs:__imp_NdisReadConfiguration
0x1400f76d9  nop     dword ptr [rax+rax+00h]
0x1400f76de  cmp     [rsp+2E0h+Status], esi
0x1400f76e2  jnz     short loc_1400F76FC
0x1400f76e4  mov     r8, [rsp+2E0h+ParameterValue]
0x1400f76e9  lea     rdx, VmsMiniCommonIp4UdpChecksum
0x1400f76f0  mov     rcx, rdi
0x1400f76f3  mov     r8d, [r8+8]
0x1400f76f7  call    VmsMpCommonSetOffload
0x1400f76fc  mov     r8, [rsp+2E0h+ConfigurationHandle]; ConfigurationHandle
0x1400f7701  lea     r9, VmsMiniCommonIp6UdpChecksum; Keyword
0x1400f7708  lea     rdx, [rsp+2E0h+ParameterValue]; ParameterValue
0x1400f770d  mov     dword ptr [rsp+2E0h+Timeout], esi; ParameterType
0x1400f7711  lea     rcx, [rsp+2E0h+Status]; Status
0x1400f7716  call    cs:__imp_NdisReadConfiguration
0x1400f771d  nop     dword ptr [rax+rax+00h]
0x1400f7722  cmp     [rsp+2E0h+Status], esi
0x1400f7726  jnz     short loc_1400F7740
0x1400f7728  mov     r8, [rsp+2E0h+ParameterValue]
0x1400f772d  lea     rdx, VmsMiniCommonIp6UdpChecksum
0x1400f7734  mov     rcx, rdi
0x1400f7737  mov     r8d, [r8+8]
0x1400f773b  call    VmsMpCommonSetOffload
0x1400f7740  mov     r8, [rsp+2E0h+ConfigurationHandle]; ConfigurationHandle
0x1400f7745  lea     r9, VmsMiniCommonIp4TcpLsoV2; Keyword
0x1400f774c  lea     rdx, [rsp+2E0h+ParameterValue]; ParameterValue
0x1400f7751  mov     dword ptr [rsp+2E0h+Timeout], esi; ParameterType
  ... truncated ...
```
